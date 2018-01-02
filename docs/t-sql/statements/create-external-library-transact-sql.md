---
title: "CREATE EXTERNAL LIBRARY (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/05/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "t-sql|statements"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "CREATE EXTERNAL LIBRARY"
  - "CREATE_EXTERNAL_LIBRARY_TSQL"
  - "EXTERNAL LIBRARY"
  - "EXTERNAL_LIBRARY_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "CREATE EXTERNAL LIBRARY"
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# CREATE EXTERNAL LIBRARY (Transact-SQL)  

[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]  

Uploads R packages to a database from the specified byte stream or file path.

This statement serves as a generic mechanism for the database administrator to upload artifacts needed for any new external language runtimes (R, Python, Java, etc.) and OS platforms supported by [!INCLUDE[ssnoversion](../../includes/ssnoversion.md)]. Currently only the R language and Windows platform are supported.

## Syntax

```
CREATE EXTERNAL LIBRARY library_name  
    [ AUTHORIZATION owner_name ]  
FROM <file_spec> [,…2]  
WITH ( LANGUAGE = 'R' )  
[ ; ]  

<file_spec> ::=  
{  
(CONTENT = { <client_library_specifier> | <library_bits> }  
[, PLATFORM = WINDOWS ])  
}  

<client_library_specifier> :: =  
  '[\\computer_name\]share_name\[path\]manifest_file_name'  
| '[local_path\]manifest_file_name'  
| '<relative_path_in_external_data_source>'  

<library_bits> :: =  
{ varbinary_literal | varbinary_expression }  
```

### Arguments

**library_name**

Libraries are added to the database scoped to the user. That is, library names are considered unique within the context of a specific user or owner, and library names must be unique per user. For example, two users **RUser1** and **RUser2** can both individually and separately upload the R library `ggplot2`.

**owner_name**

Specifies the name of the user or role that owns the external library. If not specified, ownership is given to the current user.

The libraries owned by database owner are considered global to the database and runtime. In other words, database owners can create libraries that contain a common set of libraries or packages that are shared by many users. When an external library is created by a user other than the `dbo` user, the external library is private to that user only.

When the user **RUser1** executes an R script, the value of `libPath` can contain multiple paths. The first path is always the path to the shared library created by the database owner. The second part of `libPath` specifies the path containing packages uploaded individually by **RUser1**.

**file_spec**

Specifies the content of the package for a specific platform. Only one file artifact per platform is supported.

The file can be specified in the form of a local path, or network path.

Optionally, an OS platform for the file can be specified. Only one file artifact or content is permitted for each OS platform for a specific language or runtime.

**library_bits**

Specifies the content of the package as a hex literal, similar to assemblies. This option allows users to create a library to alter the library if they have the required permission, but do not have file path access to any folder the server can access.

**PLATFORM = WINDOWS**

Specifies the platform for the content of the library. The value defaults to the host platform on which SQL Server is running. Therefore, the user doesn’t have to specify the value. It is required in case where multiple platforms are supported, or the user needs to specify a different platform. Windows is the only supported platform.

## Remarks

For the R language, when using a file, packages must be prepared in the form of zipped archive files with the .ZIP extension for Windows. Currently, only the Windows platform is supported

The `CREATE EXTERNAL LIBRARY` statement only uploads the library bits to the database. The library is not actually installed until a user runs an external script afterwards, by executing [sp_execute_external_script](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md).  

Libraries uploaded to the instance can be either public or private. If the library is created by a member of `dbo`, the library is public and can be shared with all users. Otherwise, the library is private to that user only.

You cannot use blobs as a data source in the SQL Server 2017 release.

## Permissions

Requires the `CREATE ANY EXTERNAL LIBRARY` permission.

To modify a library requires the separate permission, `ALTER ANY EXTERNAL LIBRARY`.

## Examples

### A. Add an external library to a database  

The following example adds an external library called customPackage to a database.

```sql
CREATE EXTERNAL LIBRARY customPackage 
FROM 
  (CONTENT = 'C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\customPackage.zip')
WITH (LANGUAGE = 'R');
```  

After the library has been successfully uploaded to the instance, a user executes the `sp_execute_external_script` procedure, to install the library.

```sql
EXEC sp_execute_external_script 
@language =N'R', 
@script=N'
# load customPackage
library(customPackage)
'
```

### B. Installing packages with dependencies

If `packageB` has a dependency on `packageA`, then follow these general principles:

+ Upload both the target package and its dependencies.

    Both packages must be in a folder that is accessible to the server.

    ```sql
    CREATE EXTERNAL LIBRARY packageA 
    FROM (CONTENT = 'C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\packageA.zip') 
    WITH (LANGUAGE = 'R'); 
    
    CREATE EXTERNAL LIBRARY packageB FROM (CONTENT = 'C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\packageB.zip') 
    WITH (LANGUAGE = 'R');
    ```

+ Dependencies are installed first.

    If a required package `packageA` has already been uploaded to the instance, it need not have been installed separately. The required package `packageA` will be installed when `sp_execute_external_script` is first run to install  package `packageB`.

    However, if the required package,  `packageA`, is not available, installation of the target package `packageB` will fail.

    ```sql
    EXEC sp_execute_external_script 
    @language =N'R', 
    @script=N'
    # load packageB
    library(packageB)
    # call customPackageBFunc
    OutputDataSet <- customPackageBFunc()
    '
    with result sets (([result] int));    
    ```

### C. Create a library from a byte stream

The following example creates a library by passing updated bits as a hexidecimal literal.

```SQL
CREATE EXTERNAL LIBRARY customLibrary FROM (CONTENT = 0xabc123) WITH (LANGUAGE = 'R');
```

### D. Change an existing package library

The `ALTER EXTERNAL LIBRARY` DDL statement can be used to add new library content or modify existing library content. To modify an existing library requires the `ALTER ANY EXTERNAL LIBRARY` permission.

For more information, see [ALTER EXTERNAL LIBRARY](alter-external-library-transact-sql.md).

### E. Delete a package library

To delete a package library from the database, run the statement:

```sql
DROP EXTERNAL LIBRARY customPackage <user_name>;
```

> [!NOTE]
> Unlike other `DROP` statements in [!INCLUDE[ssnoversion](../../includes/ssnoversion.md)], this statement supports an optional parameter that specifies the user authority. This option allows users with ownership roles to delete libraries uploaded by regular users.

## See also

[ALTER EXTERNAL LIBRARY (Transact-SQL)](alter-external-library-transact-sql.md)  
[DROP EXTERNAL LIBRARY (Transact-SQL)](drop-external-library-transact-sql.md)  
[sys.external_library_files](../../relational-databases/system-catalog-views/sys-external-library-files-transact-sql.md)  
[sys.external_libraries](../../relational-databases/system-catalog-views/sys-external-libraries-transact-sql.md)  
