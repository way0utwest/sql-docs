---
title: "MSSQLSERVER_30089 | Microsoft Docs"
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
  - "9992 (Database Engine error)"
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_30089
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|30089|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|IFTS_FDHOST_TERMINATEDABNORMAL|  
|Message Text|The fulltext filter daemon host (FDHost) process has stopped abnormally. This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing. The process will be restarted automatically.|  
  
## Explanation  
The full-text filter daemon host has encountered some problem that has forced it to stop abnormally. The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.  
  
## User Action  
Typically, the daemon will recover from the error. If it is consistently failing, troubleshooting is necessary. Try the following to isolate the issue:  
  
1.  If a new linguistic component has been installed recently, remove it from the system.  
  
2.  Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.  
  
## See Also  
[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql.md)  
[Configure and Manage Word Breakers and Stemmers for Search](~/relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md)  
[Configure and Manage Filters for Search](~/relational-databases/search/configure-and-manage-filters-for-search.md)  
  
