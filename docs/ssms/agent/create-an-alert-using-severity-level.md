---
title: "Create an Alert Using Severity Level | Microsoft Docs"
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
  - "alerts [SQL Server], creating"
  - "SQL Server Agent, alerts"
  - "severity levels [SQL Server]"
  - "alerts [SQL Server], severity levels"
ms.assetid: a1fd71bf-5bf9-4ce2-9a1d-032576a4a6e9
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Create an Alert Using Severity Level
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent alert that is raised when an event of a specific severity level occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] or [!INCLUDE[tsql](../../includes/tsql_md.md)].  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Limitations and Restrictions](#Restrictions)  
  
    [Security](#Security)  
  
-   **To create an alert using severity level, using:**  
  
    [SQL Server Management Studio](#SSMSProcedure)  
  
    [Transact-SQL](#TsqlProcedure)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.  
  
-   Events generated with **xp_logevent** occur in the master database. Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.  
  
-   Severity levels from 19 through 25 send a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] message to the [!INCLUDE[msCoName](../../includes/msconame_md.md)] Windows application log and trigger an alert. Events with severity levels less than 19 will trigger alerts only if you have used **sp_altermessage**, RAISERROR WITH LOG, or **xp_logevent** to force them to be written to the Windows application log.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To create an alert using severity level  
  
1.  In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using severity level.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Right-click **Alerts** and select **New Alert**.  
  
4.  In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.  
  
5.  In the **Type** list, select **SQL Server event alert**.  
  
6.  Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.  
  
7.  Under **Alerts will be raised based on**, click **Severity** and then select the specific severity that will raise the alert.  
  
8.  Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**. The maximum number of characters is 100.  
  
9. Click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To create an alert using severity level  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up
    -- the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up
    -- the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The DB will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
For more information, see [sp_add_alert (Transact-SQL)](http://msdn.microsoft.com/en-us/d9b41853-e22d-4813-a79f-57efb4511f09).  
  
