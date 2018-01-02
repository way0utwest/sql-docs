---
title: "Deploy the R model and use it in SQL (walkthrough) | Microsoft Docs"
ms.custom: ""
ms.date: "07/26/2017"
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: 
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "tutorial"
applies_to: 
  - "SQL Server 2016"
dev_langs: 
  - "R"
ms.assetid: f28a7aac-6d08-4781-ad28-b48d18cc16a0
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Deploy the R model and use it in SQL

In this lesson, you use your R models in a production environment, by calling a trained model from a stored procedure. You can then invoke the stored procedure from R or any application programming language that supports [!INCLUDE[tsql](../../includes/tsql-md.md)] (such as C#, Java, Python, etc.), to use the model to make predictions on new observations.

This sample demonstrates the two most common ways to use a model in scoring:

- **Batch scoring mode** is used when you need to create multiple predictions very fast, by passing a SQL query or table as input. A table of results is returned, which you might insert directly into a table or write to a file.

- **Individual scoring mode** is used when you need to create predictions one at a time. You pass a set of individual values to the stored procedure. The values correspond to features in the model, which the model uses to create a prediction, or generate another result such as a probability value. You can then return that value to the application, or user.

## Batch scoring

A stored procedure for batch scoring was created when you initially ran the PowerShell script. This stored procedure, *PredictTipBatchMode*, does the following:

- Gets a set of input data as a SQL query
- Calls the trained logistic regression model that you saved in the previous lesson
- Predicts the probability that the driver gets any non-zero tip

1. Take a minute to look over the script for the stored procedure, *PredictTipBatchMode*. It illustrates several aspects of how a model can be operationalized using [!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)].
  
    ```tsql
    CREATE PROCEDURE [dbo].[PredictTipBatchMode]
    @input nvarchar(max)
    AS
    BEGIN
      DECLARE @lmodel2 varbinary(max) = (SELECT TOP 1 model  FROM nyc_taxi_models);
      EXEC sp_execute_external_script @language = N'R',
         @script = N'
           mod <- unserialize(as.raw(model));
           print(summary(mod))
           OutputDataSet<-rxPredict(modelObject = mod,
             data = InputDataSet,
             outData = NULL,
             predVarNames = "Score", type = "response",
             writeModelVars = FALSE, overwrite = TRUE);
           str(OutputDataSet)
           print(OutputDataSet)',
      @input_data_1 = @input,
      @params = N'@model varbinary(max)',
      @model = @lmodel2
      WITH RESULT SETS ((Score float));
    END
    ```

    + You use a SELECT statement to call the stored model from a SQL table. The model is retrieved from the table as **varbinary(max)** data, stored in the SQL variable _@lmodel2_, and passed as the parameter *mod* to the system stored procedure [sp_execute_external_script](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md).

    + The data used as inputs for scoring is defined as a SQL query and stored as a string in the SQL variable _@input_. As data is retrieved from the database, it is stored in a data frame called *InputDataSet*, which is just the default name for input data to the [sp_execute_external_script](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md) procedure; you can define another variable name if needed by using the parameter *_@input_data_1_name_*.

    + To generate the scores, the stored procedure calls the `rxPredict` function from the **RevoScaleR** library.

    + The return value, *Score*, is the probability, given the model, that driver gets a tip. Optionally, you could easily apply some kind of filter to the returned values to categorize the return values into "tip" and "no tip" groups.  For example, a probability of less than 0.5 would mean a tip is unlikely.
  
2.  To call the stored procedure in batch mode, you define the query required as input to the stored procedure. Here is the SQL query; you can run it in SSMS to verify that it works.

    ```SQL
    SELECT TOP 10
      a.passenger_count AS passenger_count,
      a.trip_time_in_secs AS trip_time_in_secs,
      a.trip_distance AS trip_distance,
      a.dropoff_datetime AS dropoff_datetime,
      dbo.fnCalculateDistance( pickup_latitude, pickup_longitude, dropoff_latitude, dropoff_longitude) AS direct_distance
      FROM 
        (SELECT medallion, hack_license, pickup_datetime, passenger_count,trip_time_in_secs,trip_distance, dropoff_datetime, pickup_latitude, pickup_longitude, dropoff_latitude, dropoff_longitude 
        FROM nyctaxi_sample)a 
      LEFT OUTER JOIN
      ( SELECT medallion, hack_license, pickup_datetime
      FROM nyctaxi_sample  tablesample (1 percent) repeatable (98052)  )b
      ON a.medallion=b.medallion
      AND a.hack_license=b.hack_license
      AND a.pickup_datetime=b.pickup_datetime
      WHERE b.medallion is null
    ```

3. Use this R code to create the input string from the SQL query:

    ```R
    input <- "N'SELECT TOP 10 a.passenger_count AS passenger_count, a.trip_time_in_secs AS trip_time_in_secs, a.trip_distance AS trip_distance, a.dropoff_datetime AS dropoff_datetime, dbo.fnCalculateDistance(pickup_latitude, pickup_longitude, dropoff_latitude, dropoff_longitude) AS direct_distance FROM (SELECT medallion, hack_license, pickup_datetime, passenger_count,trip_time_in_secs,trip_distance, dropoff_datetime, pickup_latitude, pickup_longitude, dropoff_latitude, dropoff_longitude FROM nyctaxi_sample)a LEFT OUTER JOIN ( SELECT medallion, hack_license, pickup_datetime FROM nyctaxi_sample  tablesample (1 percent) repeatable (98052)  )b ON a.medallion=b.medallion AND a.hack_license=b.hack_license AND  a.pickup_datetime=b.pickup_datetime WHERE b.medallion is null'";
    q <- paste("EXEC PredictTipBatchMode @inquery = ", input, sep="");
    ```

4. To run the stored procedure from R, call the **sqlQuery** method of the **RODBC** package and use the SQL connection `conn` that you defined earlier:

    ```R
    sqlQuery (conn, q);
    ```

    If you get an ODBC error, check the query syntax, and whether you have the right number of quotation marks. 
    
    If you get a permissions error, make sure the login has the ability to execute the stored procedure.

## Single row scoring

When calling the model for prediction on a row-by-row basis, you pass a set of values that represent features for each individual case. The stored procedure then returns a single prediction or probability. 

The stored procedure *PredictTipSingleMode* demonstrates this approach. It takes as input multiple parameters representing feature values (for example, passenger count and trip distance), scores these features using the stored R model, and outputs the tip probability.

1. If the stored procedure *PredictTipSingleMode* was not created by the initial PowerShell script, you can run the following Transact-SQL statement to create it now.

    ```tsql
    CREATE PROCEDURE [dbo].[PredictTipSingleMode] @passenger_count int = 0,
    @trip_distance float = 0,
    @trip_time_in_secs int = 0,
    @pickup_latitude float = 0,
    @pickup_longitude float = 0,
    @dropoff_latitude float = 0,
    @dropoff_longitude float = 0
    AS
    BEGIN
      DECLARE @inquery nvarchar(max) = N'
        SELECT * FROM [dbo].[fnEngineerFeatures](@passenger_count, @trip_distance, @trip_time_in_secs, @pickup_latitude, @pickup_longitude, @dropoff_latitude, @dropoff_longitude)'
      DECLARE @lmodel2 varbinary(max) = (SELECT TOP 1 model FROM nyc_taxi_models);

      EXEC sp_execute_external_script @language = N'R',  @script = N'
            mod <- unserialize(as.raw(model));
            print(summary(mod))
            OutputDataSet<-rxPredict(
              modelObject = mod,
              data = InputDataSet,
              outData = NULL,
              predVarNames = "Score",
              type = "response",
              writeModelVars = FALSE,
              overwrite = TRUE);
            str(OutputDataSet)
            print(OutputDataSet)
            ',
      @input_data_1 = @inquery,
      @params = N'
      -- passthrough columns
      @model varbinary(max) ,
      @passenger_count int ,
      @trip_distance float ,
      @trip_time_in_secs int ,
      @pickup_latitude float ,
      @pickup_longitude float ,
      @dropoff_latitude float ,
      @dropoff_longitude float',
      -- mapped variables
      @model = @lmodel2 ,
      @passenger_count =@passenger_count ,
      @trip_distance=@trip_distance ,
      @trip_time_in_secs=@trip_time_in_secs ,
      @pickup_latitude=@pickup_latitude ,
      @pickup_longitude=@pickup_longitude ,
      @dropoff_latitude=@dropoff_latitude ,
      @dropoff_longitude=@dropoff_longitude
      WITH RESULT SETS ((Score float));
    END
    ```

2. In SQL Server Management Studio, you can use the [!INCLUDE[tsql](../../includes/tsql-md.md)] **EXEC** procedure (or **EXECUTE**) to call the stored procedure, and pass it the required inputs. For example, try running this statement in Management Studio:

    ```SQL
    EXEC [dbo].[PredictTipSingleMode] 1, 2.5, 631, 40.763958,-73.973373, 40.782139,-73.977303
    ```

    The values passed in here are, respectively, for the variables _passenger\_count_, _trip_distance_, _trip\_time\_in\_secs_, _pickup\_latitude_, _pickup\_longitude_, _dropoff\_latitude_, and _dropoff\_longitude_.

3. To run this same call from R code, you simply define an R variable that contains the entire stored procedure call, like this one:

    ```R
    q2 = "EXEC PredictTipSingleMode 1, 2.5, 631, 40.763958,-73.973373, 40.782139,-73.977303 ";
    ```

    The values passed in here are, respectively, for the variables _passenger\_count_, _trip\_distance_, _trip\_time\_in\_secs_, _pickup\_latitude_, _pickup\_longitude_, _dropoff\_latitude_, and _dropoff\_longitude_.

4. Call `sqlQuery` (from the **RODBC** package) and pass the connection string, together with the string variable containing the stored procedure call.

    ```R
    # predict with stored procedure in single mode
    sqlQuery (conn, q2);
    ```

    >[!TIP]
    > R Tools for Visual Studio (RTVS) provides great integration with both SQL Server and R. See this article for more examples of using RODBC with a SQL Server connection: [Working with SQL Server and R](https://docs.microsoft.com/en-us/visualstudio/rtvs/sql-server)

## Summary

Now that you have learned how to work with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data and persist trained R models to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it should be relatively easy for you to create new models based on this data set. For example, you might try creating these additional models:

- A regression model that predicts the tip amount

- A multiclass classification model that predicts whether the tip is big, medium, or small

We also recommend that you check out some of these additional samples and resources:

+ [Data science scenarios and solution templates](data-science-scenarios-and-solution-templates.md)

+ [In-database advanced analytics](sqldev-in-database-r-for-sql-developers.md)

+ [Microsoft R - Diving into Data Analysis](https://msdn.microsoft.com/microsoft-r/data-analysis-in-microsoft-r)

+ [Additional Resources](https://msdn.microsoft.com/microsoft-r/microsoft-r-more-resources)

## Previous lesson

[Build an R model and save it in SQL Server](walkthrough-build-and-save-the-model.md)

## Next steps

[SQL Server R tutorials](sql-server-r-tutorials.md)

[How to create a stored procedure using sqlrutils](../r/how-to-create-a-stored-procedure-using-sqlrutils.md)
