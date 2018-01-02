---
title: "DROP EXTERNAL LIBRARY (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "08/17/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-database"
ms.service: ""
ms.component: "t-sql|statements"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "DROP EXTERNAL LIBRARY"
  - "DROP_EXTERNAL_LIBRARY_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "DROP EXTERNAL LIBRARY"
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# DROP EXTERNAL LIBRARY (Transact-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

Deletes an existing package library.

## Syntax  

```
DROP EXTERNAL LIBRARY library_name  
[ AUTHORIZATION owner_name ];  
```

### Arguments

**library_name**

Specifies the name of an existing package library.

Libraries are scoped to the user. That is, library names are considered unique within the context of a specific user or owner.

**owner_name**

Specifies the name of the user or role that owns the external library.

Database owners can delete libraries created by other users.

### Return values

An informational message is returned if the statement was successful.

## Remarks

Unlike other `DROP` statements in SQL Server, this statement supports specifying an optional authorization clause. This allows **dbo** or users in the **db_owner** role to drop a package library uploaded by a regular user in the database.

## Examples

Add a custom R package, named `customPackage`, to a database:

```sql
CREATE EXTERNAL LIBRARY customPackage 
FROM 'C:\Users\Username\CustomPackages\customPackage.zip';
```

Delete the `customPackage` library.

```sql
DROP EXTERNAL LIBRARY customPackage <user_name>;
```

## See also  
[CREATE EXTERNAL LIBRARY (Transact-SQL)](create-external-library-transact-sql.md)  
[ALTER EXTERNAL LIBRARY (Transact-SQL)](alter-external-library-transact-sql.md)  
[sys.external_library_files](../../relational-databases/system-catalog-views/sys-external-library-files-transact-sql.md)  
[sys.external_libraries](../../relational-databases/system-catalog-views/sys-external-libraries-transact-sql.md)  

