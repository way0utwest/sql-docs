---
title: "sys.column_encryption_keys  (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/28/2015"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-data-warehouse"
ms.service: ""
ms.component: "system-catalog-views"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
applies_to: 
  - "Azure SQL Database"
  - "SQL Server 2016 Preview"
f1_keywords: 
  - "sys.column_encryption_keys"
  - "column_encryption_keys_TSQL"
  - "sys.column_encryption_keys_TSQL"
  - "column_encryption_keys"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.column_encryption_keys catalog view"
ms.assetid: 43980dd8-b9b1-4869-a304-2c183ae8977d
caps.latest.revision: 9
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# sys.column_encryption_keys  (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-xxx-md.md)]

  Returns information about column encryption keys (CEKs) created with the [CREATE COLUMN ENCRYPTION KEY](../../t-sql/statements/create-column-encryption-key-transact-sql.md) statement. Each row represents a CEK.  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|The name of the CMK.|  
|**column_encryption_key_id**|**int**|ID of the CEK.|  
|**create_date**|**datetime**|Date the CEK was created.|  
|**modify_date**|**datetime**|Date the CEK was last modified.|  
  
## Permissions  
 Requires the **VIEW ANY COLUMN ENCRYPTION KEY** permission.  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] For more information, see [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## See Also  
 [CREATE COLUMN ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-column-encryption-key-transact-sql.md)   
 [ALTER COLUMN ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/alter-column-encryption-key-transact-sql.md)   
 [DROP COLUMN ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-column-encryption-key-transact-sql.md)   
 [CREATE COLUMN MASTER KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-column-master-key-transact-sql.md)   
 [Security Catalog Views &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [Always Encrypted &#40;Database Engine&#41;](../../relational-databases/security/encryption/always-encrypted-database-engine.md)   
 [sys.column_encryption_key_values &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-column-encryption-key-values-transact-sql.md)  
  
  
