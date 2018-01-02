---
title: "R and SQL data types and data objects (R in SQL quickstart) | Microsoft Docs"
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
dev_langs: 
  - "R"
  - "SQL"
ms.assetid: 1a17fc5b-b8c5-498f-b8b1-3b7b43a567e1
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
ms.workload: "On Demand"
---
# R and SQL data types and data objects (R in SQL quickstart)

In this step, you learn about some common issues that arise when moving data between R and SQL Server:

+ Data types sometimes do not match
+ Implicit conversions might take place
+ Cast and convert operations are sometimes required
+ R and SQL use different data objects

## Always return R data as a data frame

When your script returns results from R to SQL Server, it must return the data as a **data.frame**. Any other type of object that you generate in your script — whether that be a list, factor, vector, or binary data — must be converted to a data frame if you want to output it as part of the stored procedure results. Fortunately, there are multiple R functions to support changing other objects to a data frame. You can even serialize a binary model and return it in a data frame, which you'll do later in this tutorial.

First, let's experiment with some R basic R objects — vectors, matrices, and lists — and see how conversion to a data frame changes the output passed to SQL Server.

Compare these two "Hello World" scripts in R. The scripts look almost identical, but the first returns a single column of three values, whereas the second returns three columns with a single value each.

**Example 1**

```sql
EXECUTE sp_execute_external_script
       @language = N'R'
     , @script = N' mytextvariable <- c("hello", " ", "world");
       OutputDataSet <- as.data.frame(mytextvariable);'
     , @input_data_1 = N' ';
```

**Example 2**

```sql
EXECUTE sp_execute_external_script
        @language = N'R'
      , @script = N' OutputDataSet<- data.frame(c("hello"), " ", c("world"));'
      , @input_data_1 = N'  ';
```

## Identifying the schema and data types of R data

Why are the results so different?

The answer can usually be found by using the R `str()` command. Add the function `str(object_name)` anywhere in your R script to have the data schema of the specified R object returned as an informational message. To view messages, see in the **Messages** pane of Visual Studio Code, or the **Messages** tab in SSMS.

To figure out why Example 1 and Example 2 have such different results, insert the line `str(OutputDataSet)` at the end of the _@script_ variable definition in each statement, like this:

**Example 1 with str function added**

```sql
EXECUTE sp_execute_external_script
        @language = N'R'
      , @script = N' mytextvariable <- c("hello", " ", "world");
      str(OutputDataSet);'
      , @input_data_1 = N'  '
;
```

**Example 2 with str function added**

```sql
EXECUTE sp_execute_external_script
  @language = N'R', 
  @script = N' OutputDataSet <- data.frame(c("hello"), " ", c("world"));
    str(OutputDataSet)' , 
  @input_data_1 = N'  ';
```

Now, review the text in **Messages** to see why the output is different.

**Results - Example 1**

```
STDOUT message(s) from external script:
'data.frame':	3 obs. of  1 variable:
$ mytextvariable: Factor w/ 3 levels " ","hello","world": 2 1 3
```

**Results - Example 2**

```
STDOUT message(s) from external script:
'data.frame':	1 obs. of  3 variables:
$ c..hello..: Factor w/ 1 level "hello": 1
$ X...      : Factor w/ 1 level " ": 1
$ c..world..: Factor w/ 1 level "world": 1
```

As you can see, a slight change in R syntax had a big effect on the schema of the results. We won't go into why, because the differences in R data types are explained more thoroughly in this article by Hadley Wickham: [R Data Structures](http://adv-r.had.co.nz/Data-structures.html).

For now, just be aware that you need to check the expected results when coercing R objects into data frames.

> [!TIP]
> 
> You can also use R identity functions, such as `is.matrix`, `is.vector`, etc.

## Implicit conversion of data objects

Each R data object has its own rules for how values are handled when combined with other data objects if the two data objects have the same number of dimensions, or if any data object contains heterogenous data types.

For example, assume you run the following statement to perform matrix multiplication using R.  You multiply a single-column matrix with the three values by an array with four values, and expect a 4x3 matrix as a result.

```sql
EXECUTE sp_execute_external_script
    @language = N'R'
    , @script = N'
        x <- as.matrix(InputDataSet);
        y <- array(12:15);
    OutputDataSet <- as.data.frame(x %*% y);'
    , @input_data_1 = N' SELECT [Col1]  from RTestData;'
    WITH RESULT SETS (([Col1] int, [Col2] int, [Col3] int, Col4 int));
```

Under the covers, the column of three values is converted to a single-column matrix. Because a matrix is just a special case of an array in R, the array `y` is implicitly coerced to a single-column matrix to make the two arguments conform.

**Results**

|Col1|Col2|Col3|Col4|
|---|---|---|---|
|12|13|14|15|
|120|130|140|150|
|1200|1300|1400|1500|

However, note what happens when you change the size of the array `y`.

```sql
execute sp_execute_external_script
   @language = N'R'
   , @script = N'
        x <- as.matrix(InputDataSet);
        y <- array(12:14);
   OutputDataSet <- as.data.frame(y %*% x);'
   , @input_data_1 = N' SELECT [Col1]  from RTestData;'
   WITH RESULT SETS (([Col1] int ));
```

Now R returns a single value as the result.

**Results**
    
|Col1|
|---|
|1542|

Why? In this case, because the two arguments can be handled as vectors of the same length, R returns the inner product as a matrix.  This is the expected behavior according to the rules of linear algebra; however, it could cause problems if your downstream application expects the output schema to never change!

> [!TIP]
> 
> Getting errors? These examples require the table **RTestData**. If you haven't created the test data table, go back to this topic: [Working with inputs and outputs](../tutorials/rtsql-working-with-inputs-and-outputs.md).
> 
> If you have created the table but still get an error, make sure that you are running the stored procedure in the context of the database that contains the table, and not in **master** or another database.
> 
> Also, we suggest that you avoid using temporary tables for these examples. Some R clients will terminate a connection between batches, deleting temporary tables.

## Merge or multiply columns of different length

R provides great flexibility for working with vectors of different sizes, and for combining these column-like structures into data frames. Lists of vectors can look like a table, but they don't follow all the rules that govern database tables.

For example, the following script defines a numeric array of length 6 and stores it in the R variable `df1`. The numeric array is then combined with the integers of the RTestData table, which contains three (3) values, to make a new data frame, `df2`.

```sql
EXECUTE sp_execute_external_script
    @language = N'R'
    , @script = N'
               df1 <- as.data.frame( array(1:6) );
               df2 <- as.data.frame( c( InputDataSet , df1 ));
               OutputDataSet <- df2'
    , @input_data_1 = N' SELECT [Col1]  from RTestData;'
    WITH RESULT SETS (( [Col2] int not null, [Col3] int not null ));
```

To fill out the data frame, R repeats the elements retrieved from RTestData as many times as needed to match the number of elements in the array `df1`.

**Results**
    
|*Col2*|*Col3*|
|----|----|
|1|1|
|10|2|
|100|3|
|1|4|
|10|5|
|100|6|

Remember that a data frame only looks like a table, and is actually a list of vectors.

## Cast or convert SQL Server data

R and SQL Server don't use the same data types, so when you run a query in SQL Server to get data and then pass that to the R runtime, some type of implicit conversion usually takes place. Another set of conversions takes place when you return data from R to SQL Server.

- SQL Server pushes the data from the query to the R process managed by the Launchpad service and converts it to an internal representation for greater efficiency.
- The R runtime loads the data into a data.frame variable and performs its own operations on the data.
- The database engine returns the data to SQL Server using a secured internal connection and presents the data in terms of SQL Server data types.
- You get the data by connecting to SQL Server using a client or network library that can issue SQL queries and handle tabular data sets. This client application can potentially affect the data in other ways.

To see how this works, run a query such as this one on the AdventureWorksDW data warehouse. This view returns sales data used in creating forecasts.

```sql
SELECT ReportingDate
         , CAST(ModelRegion as varchar(50)) as ProductSeries
         , Amount
           FROM [AdventureWorksDW2014].[dbo].[vTimeSeries]
           WHERE [ModelRegion] = 'M200 Europe'
           ORDER BY ReportingDate ASC
```

> [!NOTE]
> 
> You can use any version of AdventureWorks, or create a different query using a database of your own. The point is to try to handle some data that contains text, datetime and numeric values.

Now, try pasting this query as the input to the stored procedure.

```sql
EXECUTE sp_execute_external_script
       @language = N'R'
      , @script = N' str(InputDataSet);
      OutputDataSet <- InputDataSet;'
      , @input_data_1 = N'
           SELECT ReportingDate
         , CAST(ModelRegion as varchar(50)) as ProductSeries
         , Amount
           FROM [AdventureWorksDW2014].[dbo].[vTimeSeries]
           WHERE [ModelRegion] = ''M200 Europe''
           ORDER BY ReportingDate ASC ;'
WITH RESULT SETS undefined;
```

If you get an error, you'll probably need to make some edits to the query text. For example, the string predicate in the WHERE clause must be enclosed by two sets of single quotation marks.

After you get the query working, review the results of the `str` function to see how R treats the input data.

**Results**

```
STDOUT message(s) from external script: 'data.frame':    37 obs. of  3 variables:
STDOUT message(s) from external script: $ ReportingDate: POSIXct, format: "2010-12-24 23:00:00" "2010-12-24 23:00:00"
STDOUT message(s) from external script: $ ProductSeries: Factor w/ 1 levels "M200 Europe",..: 1 1 1 1 1 1 1 1 1 1
STDOUT message(s) from external script: $ Amount       : num  3400 16925 20350 16950 16950
```

+ The datetime column has been processed using the R data type, **POSIXct**.
+ The text column "ProductSeries" has been identified as a **factor**, meaning a categorical variable. String values are handled as factors by default. If you pass a string to R, it is converted to an integer for internal use, and then mapped back to the string on output.

### Summary

From even these short examples, you can see the need to check the effects of data conversion when passing SQL queries as input. Because some SQL Server data types are not supported by R, consider these ways to avoid errors:

+ Test your data in advance and verify columns or values in your schema that could be a problem when passed to R code.
+ Specify columns in your input data source individually, rather than using `SELECT *`, and know how each column will be handled.
+ Perform explicit casts as necessary when preparing your input data, to avoid surprises.
+ Avoid passing columns of data (such as GUIDS or rowguids) that cause errors and aren't useful for modeling.

For more information on supported and unsupported data types, see [R libraries and data types](../r/r-libraries-and-data-types.md).

For information about the performance impact of run-time conversion of strings to numerical factors, see [SQL Server R Services performance tuning](../r/sql-server-r-services-performance-tuning.md).

## Next lesson

In the next step, you'll learn how to apply R functions to SQL Server data.

[Using R functions with SQL Server data](../../advanced-analytics/tutorials/rtsql-using-r-functions-with-sql-server-data.md)
