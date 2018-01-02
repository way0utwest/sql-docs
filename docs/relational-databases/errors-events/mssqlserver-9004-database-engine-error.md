---
title: "MSSQLSERVER_9004 | Microsoft Docs"
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
  - "9004 (Database Engine error)"
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_9004
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|9004|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|LOG_CORRUPT|  
|Message Text|An error occurred while processing the log for database '%.*ls'.  If possible, restore from backup. If a backup is not available, it might be necessary to rebuild the log.|  
  
## Explanation  
An error was encountered while processing the log during rollback, recovery, or replication. This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## User Action  
One of the following actions will correct this error:  
  
-   Restore from a backup.  
  
-   Rebuild the log.  
  
Also, check system event and error logs to identify issues within the system that may have caused the problem.  
  
