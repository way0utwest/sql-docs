---
title: "Delete One or More Jobs | Microsoft Docs"
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
  - "SQL Server Agent jobs, deleting"
  - "dropping jobs"
  - "jobs [SQL Server Agent], deleting"
  - "deleting jobs"
  - "removing jobs"
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Delete One or More Jobs
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)], [!INCLUDE[tsql](../../includes/tsql_md.md)], or SQL Server Management Objects.  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To delete a job(s), using:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To delete a job  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.  
  
3.  In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.  
  
4.  Click **OK**.  
  
#### To delete multiple jobs  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**.  
  
3.  Right-click **Job Activity Monitor**, and click **View Job Activity**.  
  
4.  In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To delete a job  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
For more information, see [sp_delete_job (Transact-SQL)](http://msdn.microsoft.com/en-us/b85db6e4-623c-41f1-9643-07e5ea38db09).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To delete multiple jobs**  
  
Use the **JobCollection** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  
