---
title: "sys.dm_exec_query_parallel_workers (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "05/24/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "dmv's"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "dm_exec_query_parallel_workers_TSQL"
  - "dm_exec_query_parallel_workers"
  - "sys.dm_exec_query_parallel_workers_TSQL"
  - "sys.dm_exec_query_parallel_workers"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.dm_exec_query_parallel_workers dynamic management view"
ms.assetid: 1d72cef1-22d8-4ae0-91db-6694fe918c9f
caps.latest.revision: 1
author: "pelopes"
ms.author: "pelopes"
manager: "ajayj"
ms.workload: "Inactive"
---
# sys.dm_exec_query_parallel_workers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-all-md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  Returns worker availability information per node.  
  
|Name|Data type|Description|  
|----------|---------------|-----------------|  
|**node_id**|**int**|NUMA node ID.|  
|**scheduler_count**|**int**|Number of schedulers on this node.|  
|**max_worker_count**|**int**|Maximum number of workers for parallel queries.|  
|**reserved_worker_count**|**int**|Number of workers reserved by parallel queries, plus number of main workers used by all requests.| 
|**free_worker_count**|**int**|Number of workers available for tasks.<br /><br />**Note:** every incoming request consumes at least 1 worker, which is subtracted from the free worker count.  It is possible that the free worker count can be a negative number on a heavily loaded server.| 
|**used_worker_count**|**int**|Number of workers used by parallel queries.|  
  
## Permissions  
 On [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires VIEW SERVER STATE permission on the server.  
  
 On [!INCLUDE[ssSDS](../../includes/sssds-md.md)] Premium Tiers requires the VIEW DATABASE STATE permission in the database. On [!INCLUDE[ssSDS](../../includes/sssds-md.md)] Standard and Basic Tiers requires the [!INCLUDE[ssSDS](../../includes/sssds-md.md)] admin account.  
  
## Examples  
  
### A. Viewing current parallel worker availability  

``` tsql 
SELECT * FROM sys.dm_exec_query_parallel_workers;  
```  
  
## See Also  
 [Dynamic Management Views and Functions &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Execution Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md)   
 [sys.dm_os_workers &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-workers-transact-sql.md)
