---
title: "Write the Job Status to the Windows Application Log | Microsoft Docs"
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
  - "status information [SQL Server], jobs"
  - "SQL Server Agent jobs, status"
  - "writing job status to log"
  - "jobs [SQL Server Agent], status"
  - "logs [SQL Server], jobs"
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Write the Job Status to the Windows Application Log
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)], [!INCLUDE[tsql](../../includes/tsql_md.md)], or SQL Server Management Objects.  
  
Job responses ensure that database administrators know when jobs complete and how frequently they run. Typical job responses include:  
  
-   Notifying the operator by using e-mail, electronic paging, or a **net send** message. Use one of these job responses if the operator must perform a follow-up action. For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.  
  
-   Writing an event message to the Windows application log. You can use this response only for failed jobs.  
  
-   Automatically deleting the job. Use this job response if you are certain that you do not need to rerun this job.  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To write the job status to the Windows application log, using:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To write job status to the Windows application log  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.  
  
3.  Select the **Notifications** page.  
  
4.  Check **Write to Windows application event log**, and choose one of the following:  
  
    -   Click**When the job succeeds**to log the job status when the job completes successfully.  
  
    -   Click**When the job fails**to log the job status when the job completes unsuccessfully.  
  
    -   Click**When the job completes** to log the job status regardless of completion status.  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To write job status to the Windows application log**  
  
Call the **EventLogLevel** property of the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.  
  
The following code example sets the job to generate an operating system event log entry when the job execution finishes.  
  
**PowerShell**  
  
```  
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
  
