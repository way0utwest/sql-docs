---
title: "Delete a Job Step Log | Microsoft Docs"
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
  - "job steps [SQL Server Agent]"
  - "deleting job step logs"
  - "logs [SQL Server], jobs"
  - "removing job step logs"
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Delete a Job Step Log
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent job step log.  
  
-   **Before you begin:**  
  
    [Limitations and Restrictions](#Restrictions)  
  
    [Security](#Security)  
  
-   **To delete a SQL Server Agent job step log, using:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
When job steps are deleted their output log is automatically deleted.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To delete a SQL Server Agent job step log  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.  
  
3.  In the **Job Properties** dialog box, delete the selected job step.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To delete a SQL Server Agent job step log  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
For more information, see [sp_delete_jobsteplog (Transact-SQL)](http://msdn.microsoft.com/en-us/e9ef4c99-abde-4038-b6a3-a25dcbaf0958).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
Use the **DeleteJobStepLogs** methods of the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see[SQL Server Management Objects (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  
```  
-- Uses PowerShell to delete all job step log files that have ID values larger than 5.  
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```  
  
