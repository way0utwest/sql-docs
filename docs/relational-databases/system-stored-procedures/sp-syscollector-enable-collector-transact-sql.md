---
title: "sp_syscollector_enable_collector (Transact-SQL) | Microsoft Docs"
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
  - "sp_syscollector_enable_collector"
  - "sp_syscollector_enable_collector_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sp_syscollector_enable_collector"
  - "data collector [SQL Server], stored procedures"
ms.assetid: 53ff2b0d-b7da-4e3d-8f3d-35e857bc3720
caps.latest.revision: 18
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sp_syscollector_enable_collector (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Enables the data collector. Because there is only one data collector per server, no parameters are required.  
  
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
dbo.sp_syscollector_enable_collector   
```  
  
## Arguments  
 None  
  
## Return Code Values  
 **0** (success) or **1** (failure)  
  
## Remarks  
 Defaults to the data collector on the server.  
  
## Permissions  
 Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.  
  
## Examples  
 The following example enables the data collector.  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector;  
```  
  
## See Also  
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Data Collection](../../relational-databases/data-collection/data-collection.md)  
  
  
