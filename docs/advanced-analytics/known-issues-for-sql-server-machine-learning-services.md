---
title: "Known issues in Machine Learning Services | Microsoft Docs"
ms.date: "11/16/2017"
ms.prod: "machine-learning-services"
ms.prod_service: "machine-learning-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b37a63a-5ff5-478e-bcc2-d13da3ac241c
caps.latest.revision: 53
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
ms.workload: "On Demand"
---
# Known issues in Machine Learning Services

This article describes known problems or limitations with machine learning components that are provided as an option in SQL Server 2016 and SQL Server 2017.

The information here applies to all of the following, unless otherwise indicated:

* SQL Server 2016

  - R Services (In-Database)
  - Microsoft R Server (Standalone)

* SQL Server 2017

  - Machine Learning Services for R (In-Database)
  - Machine Learning Services for Python (In-Database)
  - Machine Learning Server (Standalone)

## Setup and configuration issues

For a description of processes and common questions that are related to initial setup and configuration, see [Upgrade and installation FAQ](r/upgrade-and-installation-faq-sql-server-r-services.md). It contains information about upgrades, side-by-side installation, and installation of new R or Python components.

### Unable to install SQL Server machine learning features on a domain controller

If you try to install SQL Server 2016 R Services or SQL Server 2017 Machine Learning Services on a domain controller, setup fails, with these errors:

>*"An error occurred during the setup process of the feature."*
> 
>*"Cannot find group with identity..."*
> 
>*"Component error code: 0x80131509"*

The failure occurs because, on a domain controller, the service cannot create the 20 local accounts required to run machine learning. In general, we do not recommend installing SQL Server on a domain controller. For more information, see [Support bulletin 2032911](https://support.microsoft.com/en-us/help/2032911/you-may-encounter-problems-when-installing-sql-server-on-a-domain-cont).

### Install the latest service release to ensure compatibility with Microsoft R Client

If you install the latest version of Microsoft R Client and use it to run R on SQL Server in a remote compute context, you might get an error like the following:

>*You are running version 9.x.x of Microsoft R Client on your computer, which is incompatible with Microsoft R Server version 8.x.x. Download and install a compatible version.*

SQL Server 2016 requires that the R libraries on the client exactly match the R libraries on the server. The restriction has been removed for releases later than R Server 9.0.1. However, if you encounter this error, verify the version of the R libraries that's used by your client and the server and, if necessary, update the client to match the server version.

The version of R that is installed with SQL Server R Services is updated whenever a SQL Server service release is installed. To ensure that you always have the most up-to-date versions of R components, be sure to install all service packs.

To ensure compatibility with Microsoft R Client 9.0.0, install the updates that are described in this [support article](https://support.microsoft.com/kb/3210262).

To avoid problems with R packages, you can also upgrade the version of the R libraries that are installed on the server, by changing to the Modern Lifecycle policy that's described in [the next section](#bkmk_sqlbindr). When you do so, the version of R that's installed with SQL Server is updated on the same schedule that updates are published for Microsoft R Server, which ensures that both server and client always have the latest releases of Microsoft R.

**Applies to:** SQL Server 2016 R Services, with R Server version 9.0.0 or earlier

### Unable to install Python components in offline installations of SQL Server 2017 CTP 2.0 or later

If you install a pre-release version of SQL Server 2017 on a computer without internet access, the installer might fail to display the page that prompts for the location of the downloaded Python components. In such an instance, you can install the Machine Learning Services feature, but not the Python components.

This issue is fixed in the release version. If you encounter this issue, as a workaround, you can temporarily enable internet access for the duration of the setup. This limitation does not apply to R.

**Applies to:** SQL Server 2017 with Python### <a name="bkmk_sqlbindr"></a> Warning of incompatible version when you connect to an older version of SQL Server R Services from a client by using [!INCLUDE[ssSQLv14_md](../includes/sssqlv14-md.md)]

When you run R code in a SQL Server 2016 compute context, and either of the following two statements is true, you might see an error like the following:
* You installed R Server (Standalone) on a client computer by using the setup wizard for [!INCLUDE[ssSQLv14_md](../includes/sssqlv14-md.md)].
* You installed Microsoft R Server by using the [separate Windows installer](https://docs.microsoft.com/r-server/install/r-server-install-windows).

>*You are running version 9.0.0 of Microsoft R Client on your computer, which is incompatible with the Microsoft R Server version 8.0.3. Download and install a compatible version.*

You can use _binding_ in Microsoft R Server 9.0 and later releases, to upgrade the R components in SQL Server 2016 instances. To determine if support for upgrades is available for your version of R Services, see [Upgrade an instance of R Services using SqlBindR.exe](/r/use-sqlbindr-exe-to-upgrade-an-instance-of-sql-server.md).

**Applies to:** SQL Server 2016 R Services, with R Server version 9.0.0 or earlier

### Setup for SQL Server 2016 service releases might fail to install newer versions of R components

When you install a cumulative update or install a service pack for SQL Server 2016 on a computer that is not connected to the internet, the setup wizard might fail to display the prompt that lets you update the R components by using downloaded CAB files. This failure typically occurs when multiple components were installed together with the database engine.

As a workaround, you can install the service release by using the command line and specifying the */MRCACHEDIRECTORY* argument as shown in this example, which installs CU1 updates:

`C:\<path to installation media>\SQLServer2016-KB3164674-x64.exe /Action=Patch /IACCEPTROPENLICENSETERMS /MRCACHEDIRECTORY=<path to CU1 CAB files>`

To get the latest installers, see [Install machine learning components without internet access](r/installing-ml-components-without-internet-access.md).

**Applies to:** SQL Server 2016 R Services, with R Server version 9.0.0 or earlier

### Launchpad services fails to start if the version is different from the R version

If you install SQL Server R Services separately from the database engine, and the build versions are different, you might see the following error in the System Event log:

>_The SQL Server Launchpad service failed to start due to the following error: The service did not respond to the start or control request in a timely fashion._

For example, this error might occur if you install the database engine by using the release version, apply a patch to upgrade the database engine, and then add the R Services feature by using the release version.

To avoid this problem, make sure that all components have the same version number. If you upgrade one component, be sure to apply the same upgrade to all other installed components.

To view a list of the R version numbers that are required for each release of SQL Server 2016, see [Install R components without internet access](r/installing-ml-components-without-internet-access.md).

### Remote compute contexts are blocked by a firewall in SQL Server instances that are running on Azure virtual machines

If you have installed [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] on a Windows Azure virtual machine, you might not be able to use compute contexts that require the use of the virtual machine's workspace. The reason is that, by default, the firewall on Azure virtual machines includes a rule that blocks network access for local R user accounts.

As a workaround, on the Azure VM, open **Windows Firewall with Advanced Security**, select **Outbound Rules**, and disable the following rule: **Block network access for R local user accounts in SQL Server instance MSSQLSERVER**. You can also leave the rule enabled, but change the security property to **Allow if secure**.

### Implied authentication in SQLEXPRESS

When you run R jobs from a remote data-science workstation by using Integrated Windows authentication, SQL Server uses *implied authentication* to generate any local ODBC calls that might be required by the script. However, this feature did not work in the RTM build of SQL Server Express Edition.

To fix the issue, we recommend that you upgrade to a later service release.

If you cannot upgrade, you can use a SQL login to run remote R jobs that might require embedded ODBC calls.

**Applies to:** SQL Server 2016 R Services Express Edition

### Performance limits when libraries used by SQL Server are called from other tools

It is possible to call the machine learning libraries that are installed for SQL Server from an external application, such as RGui. Doing so might be the most convenient way to accomplish certain tasks, such as installing new packages, or running ad hoc tests on very short code samples. However, outside of SQL Server, performance might be limited. 

For example, even if you are using the Enterprise Edition of SQL Server, R runs in single-threaded mode when you run your R code by using external tools. To get the benefits of performance in SQL Server, initiate a SQL Server connection and use [sp_execute_external_script](../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md) to call the external script runtime.

+ In general, avoid calling the machine learning libraries that are used by SQL Server from external tools.
+ If you need to debug R or Python code, it is typically easier to do so outside of SQL Server. To get the same libraries that are in SQL Server, you can install Microsoft R Client or [Machine Learning Server](r/create-a-standalone-r-server.md).

### External script execution is throttled due to resource governance default values

In Enterprise Edition, you can use resource pools to manage external script processes. In some early release builds, the maximum memory that could be allocated to the R processes was 20 percent. Therefore, if the server had 32 GB of RAM, the R executables (RTerm.exe and BxlServer.exe) could use a maximum of 6.4 GB in a single request.

If you encounter resource limitations, check the current default. If 20 percent is not enough, see the documentation for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on how to change this value.

**Applies to:** SQL Server 2016 R Services, Enterprise Edition

## R issues

This section contains known issues that are specific to running R on SQL Server, as well as some issues that are related to the R libraries and tools published by Microsoft, including RevoScaleR.

For additional known issues that might affect R solutions, go to the [Microsoft R Server site](https://docs.microsoft.com/machine-learning-server/resources-known-issues).

### Limitations on processor affinity for R jobs

In the initial release build of SQL Server 2016, you could set processor affinity only for CPUs in the first k-group. For example, if the server is a 2-socket machine with two k-groups, only processors from the first k-group are used for the R processes. The same limitation applies when you configure resource governance for R script jobs.

This issue is fixed in SQL Server 2016 Service Pack 1. We recommend that you upgrade to the latest service release.

**Applies to:** SQL Server 2016 R Services RTM version

### Changes to column types cannot be performed when reading data in a SQL Server compute context

If your compute context is set to the SQL Server instance, you cannot use the _colClasses_ argument (or other similar arguments) to change the data type of columns in your R code.

For example, the following statement would result in an error if the column CRSDepTimeStr is not already an integer:

```r
data <- RxSqlServerData(sqlQuery = "SELECT CRSDepTimeStr, ArrDelay  FROM AirlineDemoSmall",
                                connectionString = connectionString,
                                colClasses = c(CRSDepTimeStr = "integer"))
```

As a workaround, you can rewrite the SQL query to use CAST or CONVERT and present the data to R by using the correct data type. In general, performance is better when you work with data by using SQL rather than by changing data in the R code.

**Applies to:** SQL Server 2016 R Services

### Limits on size of serialized models

When you save a model to a SQL Server table, you must serialize the model and save it in a binary format. Theoretically the maximum size of a model that can be stored with this method is 2 GB, which is the maximum size of varbinary columns in SQL Server.

If you need to use larger models, the following workarounds are available:

+ Take steps to reduce the size of your model. Some open source R packages include a great deal of information in the model object, and much of this information can be removed for deployment. 
+ Use feature selection to remove unnecessary columns.
+ If you are using an open source algorithm, consider a similar implementation using the corresponding algorithm in MicrosoftML or RevoScaleR. These packages have been optimized for deployment scenarios.
+ After the model has been rationalized and the size reduced using the preceding steps, see if the [memCompress](https://www.rdocumentation.org/packages/base/versions/3.4.1/topics/memCompress) function in base R can be used to reduce the size of the model before passing it to SQL Server. This option is best when the model is close to the 2 GB limit.
+ For larger models, you can use the SQL Server [FileTable](..\relational-databases\blob\filetables-sql-server.md) feature to store the models, rather than using a varbinary column.

    To use FileTables, you must add a firewall exception, because data stored in FileTables is managed by the Filestream filesystem driver in SQL Server, and default firewall rules block network file access. For more information, see [Enable Prerequisites for FileTable](../relational-databases/blob/enable-the-prerequisites-for-filetable.md). 

    After you have enabled FileTable, to write the model, you get a path from SQL using the FileTable API, and then write the model to that location from your code. When you need to read the model, you get the path from SQL and then call the model using the path from your script. For more information, see [Access FileTables with File Input-Output APIs](../relational-databases/blob/access-filetables-with-file-input-output-apis.md).

### Avoid clearing workspaces when you execute R code in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] compute context

If you use the R command to clear your workspace of objects while running R code in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] compute context, or if you clear the workspace as part of an R script called by using [sp_execute_external_script](../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md), you might get this error: 

>*workspace object 'revoScriptConnection' not found*

`revoScriptConnection` is an object in the R workspace that contains information about an R session that is called from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. However, if your R code includes a command to clear the workspace (such as `rm(list=ls()))`, all information about the session and other objects in the R workspace is cleared as well.

As a workaround, avoid indiscriminate clearing of variables and other objects while you're running R in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Although clearing the workspace is common when working in the R console, it can have unintended consequences.

* To delete specific variables, use the R *remove* function: `remove('name1', 'name2', ...)`.
* If there are multiple variables to delete, save the names of temporary variables to a list and perform periodic garbage collection.

### Restrictions on data that can be provided as input to an R script

You cannot use in an R script the following types of query results:

- Data from a [!INCLUDE[tsql](../includes/tsql-md.md)] query that references AlwaysEncrypted columns.
  
- Data from a [!INCLUDE[tsql](../includes/tsql-md.md)] query that references masked columns.
  
     If you need to use masked data in an R script, a possible workaround is to make a copy of the data in a temporary table and use that data instead.

### Use of strings as factors can lead to performance degradation

Using string type variables as factors can greatly increase the amount of memory used for R operations. This is a known issue with R in general, and there are many articles on the subject. For example, see [Factors are not first-class citizens in R, by John Mount, in R-bloggers)](https://www.r-bloggers.com/factors-are-not-first-class-citizens-in-r/) or [stringsAsFactors: An unauthorized biography, by Roger Peng](https://simplystatistics.org/2015/07/24/stringsasfactors-an-unauthorized-biography/). 

Although the issue is not specific to SQL Server, it can greatly affect performance of R code run in SQl Server. Strings are typically stored as varchar or nvarchar, and if a column of string data has many unique values, the process of internally converting these to integers and back to strings by R can even lead to memory allocation errors.

If you do not absolutely require a string data type for other operations, mapping the string values to a numeric (integer) data type as part of data preparation would be beneficial from a performance and scale perspective.

For a discussion of this issue, and other tips, see [Performance for R Services - data optimization](r/r-and-data-optimization-r-services.md).

### Arguments *varsToKeep* and *varsToDrop* are not supported for SQL Server data sources

When you use the rxDataStep function to write results to a table, using the *varsToKeep* and *varsToDrop* is a handy way of specifying the columns to include or exclude as part of the operation. However, these arguments are not supported for SQL Server data sources.

### Limited support for SQL data types in `sp_execute_external_script`

Not all data types that are supported in SQL can be used in R. As a workaround, consider casting the unsupported data type to a supported data type before passing the data to sp_execute_external_script.

For more information, see [R libraries and data types](r/r-libraries-and-data-types.md).

### Possible string corruption

Any round trip of string data from [!INCLUDE[tsql](../includes/tsql-md.md)] to R and then to [!INCLUDE[tsql](../includes/tsql-md.md)] again can result in corruption. This is due to the different encodings used in R and in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], as well as the various collations and languages that are supported in R and [!INCLUDE[tsql](../includes/tsql-md.md)]. Any string in a non-ASCII encoding can potentially be handled incorrectly.

When you send string data to R, convert it to an ASCII representation, if possible.

This limitation applies to data passed between SQL Server and Python as well. Multibyte characters should be passed as UTF-8 and stored as Unicode.

### Only one value of type `raw` can be returned from `sp_execute_external_script`

When a binary data type (the R **raw** data type) is returned from R, the value must be sent in the output data frame.

With data types other than **raw**, you can return parameter values along with the results of the stored procedure by adding the OUTPUT keyword. For more information, see [Parameters](https://docs.microsoft.com/sql/relational-databases/stored-procedures/parameters).

If you want to use multiple output sets that include values of type **raw**, one possible workaround is to do multiple calls of the stored procedure, or to send the result sets back to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by using ODBC.

### Loss of precision

Because [!INCLUDE[tsql](../includes/tsql-md.md)] and R support various data types, numeric data types can suffer loss of precision during conversion.

For more information about implicit data-type conversion, see [R libraries and data types](r/r-libraries-and-data-types.md).

### Variable scoping error when you use the transformFunc parameter: *The sample data set for the analysis has no variables*

To transform data while you are modeling, you can pass a *transformFunc* argument in a function such as `rxLinmod` or `rxLogit`. However, nested function calls can lead to scoping errors in the SQL Server compute context, even if the calls work correctly in the local compute context.

For example, assume that you have defined two functions, `f` and `g`, in your local global environment, and `g` calls `f`. In distributed or remote calls involving `g`, the call to `g` might fail because `f` cannot be found, even if you have passed both `f` and `g` to the remote call.

If you encounter this problem, you can work around the issue by embedding the definition of `f` inside your definition of `g`, anywhere before `g` would ordinarily call `f`.

For example:

```r
f <- function(x) { 2*x * 3 }
g <- function(y) {
              a <- 10 * y
               f(a)
}
```

To avoid the error, rewrite the definition as follows:

```r
g <- function(y){
              f <- function(x) { 2*x +3}
              a <- 10 * y
              f(a)
}
```

### Data import and manipulation using RevoScaleR

When **varchar** columns are read from a database, white space is trimmed. To prevent this, enclose strings in non-white-space characters.

When functions such as `rxDataStep` are used to create database tables that have **varchar** columns, the column width is estimated based on a sample of the data. If the width can vary, it might be necessary to pad all strings to a common length.

Using a transform to change a variable's data type is not supported when repeated calls to `rxImport` or `rxTextToXdf` are used to import and append rows, combining multiple input files into a single .xdf file.

### Limited support for rxExec

In SQL Server 2016, the `rxExec` function that's provided by the RevoScaleR package can be used only in single-threaded mode.

Parallelism for `rxExec` across multiple processes is planned for a future release.

### Increase the maximum parameter size to support rxGetVarInfo

If you use data sets with extremely large numbers of variables (for example, over 40,000), set the `max-ppsize` flag when you start R to use functions such as `rxGetVarInfo`. The `max-ppsize` flag specifies the maximum size of the pointer protection stack.

If you are using the R console (for example, in rgui.exe or rterm.exe), you can set the value of max-ppsize to 500000 by typing:

```r
R --max-ppsize=500000
```

If you are using the [!INCLUDE[rsql_developr](../includes/rsql-developr-md.md)] environment, you can set the `max-ppsize` flag by making the following call to the RevoIDE executable:

```
RevoIDE.exe /RCommandLine --max-ppsize=500000  
```

### Issues with the rxDTree function

The `rxDTree` function does not currently support in-formula transformations. In particular, using the `F()` syntax for creating factors on the fly is not supported. However, numeric data is automatically binned.

Ordered factors are treated the same as factors in all RevoScaleR analysis functions except `rxDTree`.

## Python code execution or Python package issues

This section contains known issues that are specific to running Python on SQL Server, as well as issues that are related to the Python packages published by Microsoft, including [revoscalepy](https://docs.microsoft.com/r-server/python-reference/revoscalepy/revoscalepy-package) and [microsoftml](https://docs.microsoft.com/r-server/python-reference/microsoftml/microsoftml-package).

### Call to pretrained model fails if path to model is too long

If you install the pretrained models in a default installation, depending on your machine name and instance name, the resulting complete path to the trained model file might be too long for Python to read. This limitation will be fixed in an upcoming service release.

There are several potential workarounds: 

+ When you install the pretrained models, choose a custom location.
+ If possible, install the SQL Server instance under a custom installation path, such as C:\SQL\MSSQL14.MSSQLSERVER.
+ Use the Windows utility [Fsutil](https://technet.microsoft.com/library/cc788097(v=ws.11).aspx) to create a hardlink that maps the model file to a shorter path. 

### Failure to initialize a varbinary variable causes an error in BxlServer

If you run Python code in SQL Server using `sp_execute_external_script`, and the code has output variables of type varbinary(max), varchar(max) or similar types, the variable must be initialized or set as part of your script. Otherwise, the data exchange component, BxlServer, raises an error and stops working.

This limitation will be fixed in an upcoming service release. As a workaround, make sure that the variable is initialized within the Python script. Any valid value can be used, as in the following examples:

```sql
declare @b varbinary(max);
exec sp_execute_external_script
  @language = N'Python'
  , @script = N'b = 0x0'
  , @params = N'@b varbinary(max) OUTPUT'
  , @b = @b OUTPUT;
go
```

```sql
declare @b varchar(30);
exec sp_execute_external_script
  @language = N'Python'
  , @script = N' b = ""  '
  , @params = N'@b varchar(30) OUTPUT'
  , @b = @b OUTPUT;
go
```

## Revolution R Enterprise and Microsoft R Open

This section lists issues specific to R connectivity, development, and performance tools that are provided by Revolution Analytics. These tools were provided in earlier pre-release versions of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].

In general, we recommend that you uninstall these previous versions and install the latest version of SQL Server or Microsoft R Server.

### Running side-by-side versions of Revolution R Enterprise

Installing Revolution R Enterprise side by side with any version of [!INCLUDE[rsql_productname_md](../includes/rsql-productname-md.md)] is not supported.

If you have a license to use a different version of Revolution R Enterprise, you must put it on a separate computer from both the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and any workstation that you want to use to connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance.

### The use of an R productivity environment is not supported

Some pre-release versions of [!INCLUDE[rsql_productname](../includes/rsql-productname-md.md)] included an R development environment for Windows that was created by Revolution Analytics. This tool is no longer provided, and it is not supported.

For compatibility with [!INCLUDE[rsql_productname](../includes/rsql-productname-md.md)], we strongly recommend that you install Microsoft R Client or Microsoft R Server instead of the Revolution Analytics tools. [R Tools for Visual Studio](https://www.visualstudio.com/vs/rtvs/) and [Visual Studio Code](https://code.visualstudio.com/) also supports Microsoft R solutions.

### Compatibility issues with SQLite ODBC driver and RevoScaleR

Revision 0.92 of the SQLite ODBC driver is incompatible with RevoScaleR. Revisions 0.88-0.91 and 0.93 and later are known to be compatible.


## See also

[What's new in SQL Server 2016](../sql-server/what-s-new-in-sql-server-2016.md)

[Troubleshooting machine learning in SQL Server](machine-learning-troubleshooting-faq.md)
