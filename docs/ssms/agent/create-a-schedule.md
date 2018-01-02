---
title: "Create a Schedule | Microsoft Docs"
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
  - "scheduling jobs [SQL Server]"
  - "SQL Server Agent jobs, scheduling"
  - "jobs [SQL Server Agent], scheduling"
  - "schedules [SQL Server], jobs"
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Create a Schedule
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)], [!INCLUDE[tsql](../../includes/tsql_md.md)], or SQL Server Management Objects.  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To create a schedule, using:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To create a schedule  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.  
  
3.  In the **Manage Schedules** dialog box, click **New**.  
  
4.  In the **Name** box, type a name for the new schedule.  
  
5.  If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.  
  
6.  For **Schedule Type**, select one of the following:  
  
    -   To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.  
  
    -   If you want a schedule to run repeatedly, click **Recurring**. To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.  
  
    -   If you want the schedule to run only one time, click **One time**. To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To create a schedule  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
For more information, see [sp_add_schedule (Transact-SQL)](http://msdn.microsoft.com/en-us/9060aae3-3ddd-40a5-83bb-3ea7ab1ffbd7).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To create a schedule**  
  
Use the **JobSchedule** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  
