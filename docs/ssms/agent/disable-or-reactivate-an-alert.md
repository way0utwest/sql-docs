---
title: "Disable or Reactivate an Alert | Microsoft Docs"
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
  - "SQL Server Agent, alerts"
  - "alerts [SQL Server], reactivating"
  - "deleting alerts"
  - "canceling alerts"
  - "dropping alerts"
  - "disabling alerts"
  - "alerts [SQL Server], disabling"
  - "reactivating alerts"
  - "removing alerts"
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Disable or Reactivate an Alert
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] or [!INCLUDE[tsql](../../includes/tsql_md.md)].  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To disable or reactivate an alert, using:**  
  
    [SQL Server Management Studio](#SSMSProcedure)  
  
    [Transact-SQL](#TsqlProcedure)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
By default, members of the **sysadmin** fixed server role can edit information in an alert. Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To disable or reactivate an alert  
  
1.  In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Click the plus sign to expand the **Alerts** folder.  
  
4.  Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.  
  
5.  The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process. When finished, click **Close**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To disable or reactivate an alert  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
For more information, see [sp_update_alert (Transact-SQL)](http://msdn.microsoft.com/en-us/4bbaeaab-8aca-4c9e-abc1-82ce73090bd3).  
  
