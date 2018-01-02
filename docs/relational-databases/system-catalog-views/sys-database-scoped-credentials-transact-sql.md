---
title: "sys.database_scoped_credentials (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/27/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse"
ms.service: ""
ms.component: "system-catalog-views"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sys.database_scoped_credentials"
  - "sys.database_scoped_credentials_TSQL"
  - "database_scoped_credentials"
  - "database_scoped_credentials_TSQL"
helpviewer_keywords: 
  - "sys.database_scoped_credentials catalog view"
ms.assetid: 68e8aa6b-bcdc-42aa-93d8-d498f724c188
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# sys.database_scoped_credentials (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-asdw-xxx-md.md)]

  Returns one row for each database scoped credential in the database.  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|credential_id|**int**|ID of the database scoped credential. Is unique in the database.|  
|name|**sysname**|Name of the database scoped credential. Is unique in the database.|  
|credential_identity|**nvarchar(4000)**|Name of the identity to use. This will generally be a Windows user. It does not have to be unique.|  
|create_date|**datetime**|Time at which the database scoped credential was created.|  
|modify_date|**datetime**|Time at which the database scoped credential was last modified.|  
|target_type|**nvarchar(100)**|Type of database scoped credential. Returns `NULL` for database scoped credentials.|  
|target_id|**int**|ID of the object that the database scoped credential is mapped to. Returns 0 for database scoped credentials|  
  
## Permissions  
 Requires `CONTROL` permission on the database.  
  
## See Also  
 [Credentials &#40;Database Engine&#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [CREATE DATABASE SCOPED CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)   
 [ALTER DATABASE SCOPED CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-credential-transact-sql.md)   
 [DROP DATABASE SCOPED CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-scoped-credential-transact-sql.md)   
 [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/create-credential-transact-sql.md)   
 [sys.credentials &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-credentials-transact-sql.md)  
  
  
