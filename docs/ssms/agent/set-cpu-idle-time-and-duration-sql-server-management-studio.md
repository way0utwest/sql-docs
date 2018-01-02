---
title: "Set CPU Idle Time and Duration (SQL Server Management Studio) | Microsoft Docs"
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
helpviewer_keywords: 
  - "CPU [SQL Server], idle conditions"
  - "time [SQL Server], CPU idle and duration"
  - "duration of CPU idle [SQL Server]"
  - "SQL Server Agent, CPU idle conditions"
  - "idle time [SQL Server]"
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Set CPU Idle Time and Duration (SQL Server Management Studio)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]. The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent responds to events. For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes. Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes. If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To set CPU idle time and duration  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.  
  
3.  Under **Idle CPU condition**, do the following:  
  
    -   Check **Define idle CPU condition.**  
  
    -   Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box. This sets the usage level that the CPU must fall below before it is considered idle.  
  
    -   Specify a number of seconds for the **And remains below this level for** box. This sets the duration that the minimum CPU usage must remain at before it is considered idle.  
  
