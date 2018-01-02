---
title: "Create data features using R and SQL (walkthrough) | Microsoft Docs"
ms.custom: ""
ms.date: "08/23/2017"
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
ms.assetid: 4981d4eb-0874-4fe9-82e1-edf99890e27a
caps.latest.revision: 21
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Create data features using R and SQL (walkthrough)

Data engineering is an important part of machine learning. Data often requires transformation before you can use it for predictive modeling. If the data does not have the features you need, you can engineer them from existing values.

For this modeling task, rather than using the raw latitude and longitude values of the pickup and drop-off location, you'd like to have the distance in miles between the two locations. To create this feature, you compute the direct linear distance between two points, by using the [haversine formula](https://en.wikipedia.org/wiki/Haversine_formula).

In this step, we compare two different methods for creating a feature from data:

- Using a custom R function
- Using a custom T-SQL function in [!INCLUDE[tsql](../../includes/tsql-md.md)]

The goal is to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set of data that includes the original columns plus the new numeric feature, *direct_distance*.

## Featurization using R

The R language is well-known for its rich and varied statistical libraries, but you still might need to create custom data transformations.

First, let's do it the way R users are accustomed to: get the data onto your laptop, and then run a custom R function, *ComputeDist*, which calculates the linear distance between two points specified by latitude and longitude values.

1. Remember that the data source object you created earlier gets only the top 1000 rows. So let's define a query that gets all the data.

    ```R
    bigQuery <- "SELECT tipped, fare_amount, passenger_count,trip_time_in_secs,trip_distance, pickup_datetime, dropoff_datetime,  pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude FROM nyctaxi_sample";
    ```

2. Create a new SQL Server data source using the query.

    ```R
    featureDataSource <- RxSqlServerData(sqlQuery = bigQuery,colClasses = c(pickup_longitude = "numeric", pickup_latitude = "numeric", dropoff_longitude = "numeric", dropoff_latitude = "numeric", passenger_count  = "numeric", trip_distance  = "numeric", trip_time_in_secs  = "numeric", direct_distance  = "numeric"), connectionString = connStr);
    ```

    - [RxSqlServerData](https://docs.microsoft.com/r-server/r-reference/revoscaler/rxsqlserverdata) can take either a query consisting of a valid SELECT query, provided as the argument to the _sqlQuery_ parameter, or the name of a table object, provided as the _table_ parameter.
    
    - If you want to sample data from a table, you must use the _sqlQuery_ parameter, define sampling parameters using the T-SQL TABLESAMPLE clause, and set the _rowBuffering_ argument to FALSE.

3. Run the following code to create the custom R function. ComputeDist takes in two pairs of latitude and longitude values, and calculates the linear distance between them, returning the distance in miles.

    ```R
    env <- new.env();
    env$ComputeDist <- function(pickup_long, pickup_lat, dropoff_long, dropoff_lat){
      R <- 6371/1.609344 #radius in mile
      delta_lat <- dropoff_lat - pickup_lat
      delta_long <- dropoff_long - pickup_long
      degrees_to_radians = pi/180.0
      a1 <- sin(delta_lat/2*degrees_to_radians)
      a2 <- as.numeric(a1)^2
      a3 <- cos(pickup_lat*degrees_to_radians)
      a4 <- cos(dropoff_lat*degrees_to_radians)
      a5 <- sin(delta_long/2*degrees_to_radians)
      a6 <- as.numeric(a5)^2
      a <- a2+a3*a4*a6
      c <- 2*atan2(sqrt(a),sqrt(1-a))
      d <- R*c
      return (d)
    }
    ```
  
    + The first line defines a new environment. In R, an environment can be used to encapsulate name spaces in packages and such.  You can use the `search()` function to view the environments in your workspace. To view the objects in a specific environment, type `ls(<envname>)`.
    + The lines beginning with `$env.ComputeDistance` contain the code that defines the haversine formula, which calculates the *great-circle distance* between two points on a sphere.

4. Having defined the function, you apply it to the data to create a new feature column, *direct_distance*. but before you run the transformation, change the compute context to local.

    ```R
    rxSetComputeContext("local");
    ```

5. Call the [rxDataStep](https://docs.microsoft.com/r-server/r-reference/revoscaler/rxdatastep) function to get the feature engineering data, and apply the `env$ComputeDist` function to the data in memory.

    ```R
    start.time <- proc.time();
  
    changed_ds <- rxDataStep(inData = featureEngineeringQuery,
    transforms = list(direct_distance=ComputeDist(pickup_longitude,pickup_latitude, dropoff_longitude, dropoff_latitude),
    tipped = "tipped", fare_amount = "fare_amount", passenger_count = "passenger_count",
    trip_time_in_secs = "trip_time_in_secs",  trip_distance="trip_distance",
    pickup_datetime = "pickup_datetime",  dropoff_datetime = "dropoff_datetime"),
    transformEnvir = env,
    rowsPerRead=500,
    reportProgress = 3);
  
    used.time <- proc.time() - start.time;
    print(paste("It takes CPU Time=", round(used.time[1]+used.time[2],2)," seconds, Elapsed Time=", round(used.time[3],2), " seconds to generate features.", sep=""));
    ```

    + The rxDataStep function supports various methods for modifying data in place. For more information, see this article:  [How to transform and subset data in Microsft R](https://docs.microsoft.com/r-server/r/how-to-revoscaler-data-transform)
    
    However, a couple of points worth noting regarding rxDataStep: 
    
    In other data sources, you can use the arguments *varsToKeep* and *varsToDrop*, but these are not supported for SQL Server data sources. Therefore, in this example, we've used the _transforms_ argument to specify both the pass-through columns and the transformed columns. Also, when running in a SQL Server compute context, the _inData_ argument can only take a SQL Server data source.

    The preceding code can also produce a warning message when run on larger data sets. When the number of rows times the number of columns being created exceeds a set value (the default is 3,000,000), rxDataStep returns a warning, and the number of rows in the returned data frame will be truncated. To remove the warning, you can modify the _maxRowsByCols_ argument in the rxDataStep function. However, if  _maxRowsByCols_ is too large, you might experience problems when loading the data frame into memory.

7. Optionally, you can call [rxGetVarInfo](https://docs.microsoft.com/r-server/r-reference/revoscaler/rxgetvarinfo) to inspect the schema of the transformed data source.

    ```R
    rxGetVarInfo(data = changed_ds);
    ```

## Featurization using Transact-SQL

Now, create a custom SQL function, *ComputeDist*, to accomplish the same task as the custom R function.

1. Define a new custom SQL function, named *fnCalculateDistance*. The code for this user-defined SQL function is provided as part of the PowerShell script you ran to create and configure the database.  The function should already exist in your database.

    If it does not exist, use SQL Server Management Studio to generate the function in the same database where the taxi data is stored.

    ```sql
    CREATE FUNCTION [dbo].[fnCalculateDistance] (@Lat1 float, @Long1 float, @Lat2 float, @Long2 float)
    -- User-defined function calculates the direct distance between two geographical coordinates.
    RETURNS
    AS
    BEGIN
      DECLARE @distance decimal(28, 10)
      -- Convert to radians
      SET @Lat1 = @Lat1 / 57.2958
      SET @Long1 = @Long1 / 57.2958
      SET @Lat2 = @Lat2 / 57.2958
      SET @Long2 = @Long2 / 57.2958
      -- Calculate distance
      SET @distance = (SIN(@Lat1) * SIN(@Lat2)) + (COS(@Lat1) * COS(@Lat2) * COS(@Long2 - @Long1))
      --Convert to miles
      IF @distance <> 0
      BEGIN
        SET @distance = 3958.75 * ATAN(SQRT(1 - POWER(@distance, 2)) / @distance);
      END
      RETURN @distance
    END
    ```

2. Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement from any application that supports [!INCLUDE[tsql](../../includes/tsql-md.md)], just to see how the function works.

    ```sql
    SELECT tipped, fare_amount, passenger_count,trip_time_in_secs,trip_distance, pickup_datetime, dropoff_datetime,
    dbo.fnCalculateDistance(pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude) as direct_distance,
    pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude
    FROM nyctaxi_sample
    ```
3. Having defined this function, it would be easy to create the features you want by using SQL and then insert the values directly into a new table:

    ```
    SELECT tipped, fare_amount, passenger_count,trip_time_in_secs,trip_distance, pickup_datetime, dropoff_datetime,
    dbo.fnCalculateDistance(pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude) as direct_distance,
    pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude
    INTO NewFeatureTable
    FROM nyctaxi_sample
    ```

4. However, let's see how to call the custom SQL function from R code. First, store the SQL featurization query in an R variable.

    ```R
    featureEngineeringQuery = "SELECT tipped, fare_amount, passenger_count,
        trip_time_in_secs,trip_distance, pickup_datetime, dropoff_datetime,
        dbo.fnCalculateDistance(pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude) as direct_distance,
        pickup_latitude, pickup_longitude,  dropoff_latitude, dropoff_longitude
        FROM nyctaxi_sample
        tablesample (1 percent) repeatable (98052)"
    ```
  
    > [!TIP]
    > This query has been modified to get a smaller sample of data, to make this walkthrough faster. You can remove the TABLESAMPLE clause if you want to get all the data; however, depending on your environment, it might not be possible to load the full datset into R, resulting in an error.
  
5. Use the following lines of code to call the [!INCLUDE[tsql](../../includes/tsql-md.md)] function from your R environment and apply it to the data defined in *featureEngineeringQuery*.
  
    ```R
    featureDataSource = RxSqlServerData(sqlQuery = featureEngineeringQuery,
      colClasses = c(pickup_longitude = "numeric", pickup_latitude = "numeric",
             dropoff_longitude = "numeric", dropoff_latitude = "numeric",
             passenger_count  = "numeric", trip_distance  = "numeric",
              trip_time_in_secs  = "numeric", direct_distance  = "numeric"),
      connectionString = connStr)
    ```
  
6.  Now that the new feature is created, call **rxGetVarsInfo** to create a summary of the data in the feature table.
  
    ```R
    rxGetVarInfo(data = featureDataSource)
    ```

    *Results*

    ```
    Var 1: tipped, Type: integer
    Var 2: fare_amount, Type: numeric
    Var 3: passenger_count, Type: numeric
    Var 4: trip_time_in_secs, Type: numeric
    Var 5: trip_distance, Type: numeric
    Var 6: pickup_datetime, Type: character
    Var 7: dropoff_datetime, Type: character
    Var 8: direct_distance, Type: numeric
    Var 9: pickup_latitude, Type: numeric
    Var 10: pickup_longitude, Type: numeric
    Var 11: dropoff_latitude, Type: numeric
    Var 12: dropoff_longitude, Type: numeric
    ```

    > [!NOTE]
    > In some cases, you might get an error like this one:
    > *The EXECUTE permission was denied on the object 'fnCalculateDistance'*
    > If so, make sure that the login you are using has permissions to run scripts and create objects on the database, not just on the instance.
    > Check the schema for the object, fnCalculateDistance. If the object was created by the database owner, and your login belongs to the role db_datareader, you need to give the login explicit permissions to run the script.

## Comparing R functions and SQL functions

Remember this piece of code used to time the R code?

```R
start.time <- proc.time()
<your code here>
used.time <- proc.time() - start.time
print(paste("It takes CPU Time=", round(used.time[1]+used.time[2],2)," seconds, Elapsed Time=", round(used.time[3],2), " seconds to generate features.", sep=""))
```

You can try using this with the SQL custom function example to see how long the data transformation takes when calling a SQL function. Also, try switching compute contexts with rxSetComputeContext and compare the timings.

Your times might vary significantly, depending on your network speed, and your hardware configuration. In the configurations we tested, the [!INCLUDE[tsql](../../includes/tsql-md.md)] function approach was faster than using a custom R function. Therefore, we've use the [!INCLUDE[tsql](../../includes/tsql-md.md)] function for these calculations in subsequent steps.

> [!TIP]
> Very often, feature engineering using [!INCLUDE[tsql](../../includes/tsql-md.md)] will be faster than R. For example, T-SQL includes fast windowing and ranking functions that can be applied to common data science calculations such as rolling moving averages and *n*-tiles. Choose the most efficient method based on your data and task.

## Next lesson

[Build an R model and save to SQL](walkthrough-build-and-save-the-model.md)

## Previous lesson

[View and summarize data using R](walkthrough-view-and-summarize-data-using-r.md)

