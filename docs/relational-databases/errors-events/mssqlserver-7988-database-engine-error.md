---
title: "MSSQLSERVER_7988 | Microsoft Docs"
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
  - "7988 (Database Engine error)"
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_7988
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|7988|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED|  
|Message Text|System table pre-checks: Object ID O_ID. Loop in data chain detected at P_ID. Check statement terminated because of an irreparable error.|  
  
## Explanation  
The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables. If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately. A page linkage loop has been detected on page *P_ID*. A page linkage loop occurs when the next page pointers from a page eventually return to the page.  
  
## User Action  
  
### Look for Hardware Failure  
Run hardware diagnostics and correct any problems. Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure. Fix any hardware-related problems that are contained in the logs.  
  
If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem. Check to make sure that the system does not have write-caching enabled on the disk controller. If you suspect write-caching to be the problem, contact your hardware vendor.  
  
Finally, you might find it useful to switch to a new hardware system. This switch may include reformatting the disk drives and reinstalling the operating system.  
  
### Restore from Backup  
If the problem is not hardware related and a known clean backup is available, restore the database from the backup.  
  
### Run DBCC CHECKDB  
Not applicable. This error cannot be repaired automatically. If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).  
  
