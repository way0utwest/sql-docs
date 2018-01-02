---
title: "SQL Server Agent Properties (General Page) | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-agent"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.ag.agent.general.f1"
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQL Server Agent Properties (General Page)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent service.  
  
## Options  
**Service state**  
Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent service.  
  
**Auto restart SQL Server if it stops unexpectedly**  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] stops unexpectedly.  
  
**Auto restart SQL Server Agent if it stops unexpectedly**  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent stops unexpectedly.  
  
**Filename**  
Specify the file name for the error log.  
  
**...**  
Browse to the error log file.  
  
**Include execution trace messages**  
Includes execution trace messages in the error log. Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent operation. Therefore, the log file requires more disk space when this option is selected. This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent.  
  
**Write OEM file**  
Writes the error log file as a non-Unicode file. This reduces the amount of disk space consumed by the log file. However, messages that include Unicode data may be more difficult to read when this option is enabled.  
  
**Net send recipient**  
Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent writes to the log file.  
  
## See Also  
[Operators](../../ssms/agent/operators.md)  
[SQL Server Agent Error Log](../../ssms/agent/sql-server-agent-error-log.md)  
  
