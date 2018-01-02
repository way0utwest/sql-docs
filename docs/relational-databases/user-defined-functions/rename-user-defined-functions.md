---
title: "Rename User-defined Functions | Microsoft Docs"
ms.custom: ""
ms.date: "03/16/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "udf"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "dbe-udf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Rename User-defined Functions
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]
  You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **In This Topic**  
  
-   **Before you begin:**  
  
     [Limitations and Restrictions](#Restrictions)  
  
     [Security](#Security)  
  
-   **To rename user-defined functions, using:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Before You Begin  
  
###  <a name="Restrictions"></a> Limitations and Restrictions  
  
-   Function names must comply with the rules for [identifiers](../../relational-databases/databases/database-identifiers.md).  
  
-   Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view. Therefore, we recommend that you do not rename this object type. Instead, drop and re-create the stored procedure with its new name.  
  
-   Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.  
  
###  <a name="Security"></a> Security  
  
####  <a name="Permissions"></a> Permissions  
 To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function. To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.  
  
##  <a name="SSMSProcedure"></a> Using SQL Server Management Studio  
  
#### To rename user-defined functions  
  
1.  In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then  
  
2.  Click the plus sign next to the **Programmability** folder.  
  
3.  Click the plus sign next to the folder that contains the function you wish to rename:  
  
    -   Table-valued Function  
  
    -   Scalar-valued Function  
  
    -   Aggregate Function  
  
4.  Right-click the function you wish to rename and select **Rename**.  
  
5.  Enter the function’s new name.  
  
##  <a name="TsqlProcedure"></a> Using Transact-SQL  
 **To rename user-defined functions**  
  
 This task cannot be performed using Transact-SQL statements. To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name. Ensure that all code and applications that used the function’s old name now use the new name.  
  
 For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](../../t-sql/statements/create-function-transact-sql.md) and [DROP FUNCTION &#40;Transact-SQL&#41;](../../t-sql/statements/drop-function-transact-sql.md).  
  
## See Also  
 [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql.md)   
 [View User-defined Functions](../../relational-databases/user-defined-functions/view-user-defined-functions.md)  
  
  
