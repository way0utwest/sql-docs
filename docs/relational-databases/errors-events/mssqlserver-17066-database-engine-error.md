---
title: "MSSQLSERVER_17066 | Microsoft Docs"
ms.custom: ""
ms.date: "04/04/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "errors-events"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
helpviewer_keywords: 
  - "17066 (Database Engine error)"
ms.assetid: 7d650bbf-c583-4af8-9e22-993ee2880d95
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_17066
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|17066|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|SQLASSERT_ONLY|  
|Message Text|SQL Server Assertion: File: \<%s>, line=%d Failed Assertion = '%s'. This error may be timing-related. If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.|  
  
## Explanation  
This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.  
  
## User Action  
Rerun the statement that caused the exception to fire. If the error was caused by a timing-related event, the error may not recur. If the problem persists, run DBCC CHECKDB to  check for on-disk corruption. Restart the server to ensure that the in-memory data structures are not corrupted.  
  
## See Also  
[DBCC CHECKDB &#40;Transact-SQL&#41;](~/t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
  
