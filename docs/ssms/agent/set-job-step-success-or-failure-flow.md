---
title: "Set Job Step Success or Failure Flow | Microsoft Docs"
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
  - "SQL Server Agent jobs, action flow logic"
  - "successful jobs [SQL Server]"
  - "failed jobs [SQL Server]"
  - "jobs [SQL Server Agent], action flow logic"
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Set Job Step Success or Failure Flow
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
When creating [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] should take if a failure occurs during job execution. Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] should take upon the success or failure of each job step. Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent.  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To set job step success or failure flow, using:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To set job step success or failure flow  
  
1.  In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.  
  
2.  Right-click the job you want to edit, and then click **Properties**.  
  
3.  Select the **Steps** page, click a step, and then click **Edit**.  
  
4.  In the **Job Step Properties** dialog box, select the **Advanced** page.  
  
5.  In the **On success action**list, click the action to perform if the job step completes successfully.  
  
6.  In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed. If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.  
  
7.  In the **On failure action** list, click the action to perform if the job step fails.  
  
8.  If the job is a [!INCLUDE[tsql](../../includes/tsql_md.md)] script, you can choose from the following options:  
  
    -   In the **Output file** box, enter the name of an output file to which the script output will be written. By default the file is overwritten each time the job step executes. If you do not want the output file overwritten, check **Append output to existing file**.  
  
    -   Check **Log to table** if you want to log the job step to a database table. By default the table contents are overwritten each time the job step executes. If you do not want the table contents overwritten, check **Append output to existing entry in table**. After the job step executes, you can view the contents of this table by clicking **View**.  
  
    -   Check **Include step output in history** if you want the output included in the step's history. Output will only be shown if there were no errors. Also, output may be truncated.  
  
9. If the **Run as user** list is available, select the proxy account with the credentials that the job will use.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To set job step success or failure flow  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
For more information, see [sp_add_jobstep (Transact-SQL)](http://msdn.microsoft.com/en-us/97900032-523d-49d6-9865-2734fba1c755).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To set job step success or failure flow**  
  
Use the **JobStep** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  
