---
title: "Automatically Delete a Job | Microsoft Docs"
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
  - "dropping jobs"
  - "SQL Server Agent jobs, removing"
  - "automatic job removal"
  - "jobs [SQL Server Agent], deleting"
  - "deleting jobs"
  - "removing jobs"
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Automatically Delete a Job
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] or SQL Server Management Objects.  
  
Job responses ensure that database administrators know when jobs complete and how frequently they run. Typical job responses include:  
  
-   Notifying the operator by using e-mail, electronic paging, or a **net send** message.  
  
    Use one of these job responses if the operator must perform a follow-up action. For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.  
  
-   Writing an event message to the Windows application log.  
  
    You can use this response only for failed jobs.  
  
-   Automatically deleting the job.  
  
    Use this job response if you are certain that you do not need to rerun this job.  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To specify job responses, using:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To automatically delete a job  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.  
  
3.  Select the **Notifications** page.  
  
4.  Check **Automatically delete job**, and choose one of the following:  
  
    -   Click **When the job succeeds** to delete the job status when it has completed successfully.  
  
    -   Click **When the job fails** to delete the job when it has completed unsuccessfully.  
  
    -   Click **When the job completes** to delete the job regardless of completion status.  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To automatically delete a job**  
  
Use the **DeleteLevel** property of the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  
