---
title: "Viewing the SQL Server Error Log | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "configuration-manager"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cycling SQL Server error log"
  - "viewing SQL Server error log"
  - "errors [SQL Server], logs"
  - "SQL Server error log"
  - "displaying SQL Server error log"
  - "logs [SQL Server], SQL Server error logs"
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
caps.latest.revision: 24
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Viewing the SQL Server Error Log
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to ensure that processes have completed successfully (for example, backup and restore operations, batch commands, or other scripts and processes). This can be helpful to detect any current or potential problem areas, including automatic recovery messages (particularly if an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been stopped and restarted), kernel messages, or other server-level error messages.  
  
 View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor. For more information about how to view the error log, see [Open Log File Viewer](../../relational-databases/logs/open-log-file-viewer.md). By default, the error log is located at `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` and `ERRORLOG.`*n* files.  
  
 A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, although the [sp_cycle_errorlog](../../relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql.md) system stored procedure can be used to cycle the error log files without having to restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Typically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains backups of the previous six logs and gives the most recent log backup the extension .1, the second most recent the extension .2, and so on. The current error log has no extension.  
  
 Be aware that you can also view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline or cannot start. For more information, see [View Offline Log Files](../../relational-databases/logs/view-offline-log-files.md).  
  
  
