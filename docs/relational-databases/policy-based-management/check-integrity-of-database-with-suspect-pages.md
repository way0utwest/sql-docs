---
title: "Check Integrity of Database with Suspect Pages | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "performance-monitor"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Best Practices [Database Engine]"
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
caps.latest.revision: 10
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Check Integrity of Database with Suspect Pages
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  This rule checks for user databases that have the database status set to suspect. When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.  
  
 Error 824 indicates that a logical consistency error was detected during a read operation. This error frequently indicates data corruption caused by a faulty I/O subsystem component. This is a severe error condition that threatens database integrity and must be corrected immediately.  
  
## Best Practices Recommendations  
  
-   Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.  
  
-   Complete a full database consistency check ([DBCC CHECKDB](../../t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)).  
  
-   Implement the user actions that are defined in [MSSQLSERVER_824](http://go.microsoft.com/fwlink/?LinkId=81397).  
  
## For More Information  
 [Manage the suspect_pages Table &#40;SQL Server&#41;](../../relational-databases/backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
