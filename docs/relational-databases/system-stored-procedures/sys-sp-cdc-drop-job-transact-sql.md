---
title: "sys.sp_cdc_drop_job (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "system-stored-procedures"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sys.sp_cdc_drop_job_TSQL"
  - "sp_cdc_drop_job_TSQL"
  - "sp_cdc_drop_job"
  - "sys.sp_cdc_drop_job"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sp_cdc_drop_job"
ms.assetid: e8265846-8051-4848-b28e-fac27c10bdeb
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# sys.sp_cdc_drop_job (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Removes a change data capture cleanup or capture job for the current database from msdb.  
  
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sys.sp_cdc_drop_job [ [ @job_type = ] 'job_type' ]  
```  
  
## Arguments  
 [ @job_type**=** ] '*job_type*'  
 Type of job to remove. *job_type* is **nvarchar(20)** and cannot be NULL. Valid inputs are 'capture' and 'cleanup'.  
  
## Return Code Values  
 **0** (success) or **1** (failure)  
  
## Result Sets  
 Nones  
  
## Remarks  
 sp_cdc_drop_job is called internally by [sys.sp_cdc_disable_db](../../relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql.md).  
  
## Permissions  
 Requires membership in the db_owner fixed database role.  
  
## Examples  
 The following example removes the cleanup job for the `AdventureWorks2012` database.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_cdc_drop_job @job_type = N'cleanup';  
```  
  
## See Also  
 [dbo.cdc_jobs &#40;Transact-SQL&#41;](../../relational-databases/system-tables/dbo-cdc-jobs-transact-sql.md)   
 [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql.md)   
 [sys.sp_cdc_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-add-job-transact-sql.md)  
  
  
