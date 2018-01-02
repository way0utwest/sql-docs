---
title: "Make a Target Server | Microsoft Docs"
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
  - "sql13.ag.tsxwiz.complete.f1"
  - "sql13.ag.tsxwiz.cover.f1"
  - "sql13.ag.tsxwiz.credentials.f1"
  - "sql13.ag.tsxwiz.msx.f1"
helpviewer_keywords: 
  - "Target Server Wizard"
  - "SQL Server Agent jobs, target servers"
  - "target servers [SQL Server], creating"
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Make a Target Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)], [!INCLUDE[tsql](../../includes/tsql_md.md)], or SQL Server Management Objects (SMO).  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To make a target server, using:**  
  
    [SQL Server Management Studio](#SSMSProcedure)  
  
    [Transact-SQL](#TsqlProcedure)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server. Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:  
  
-   The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<&#42;instance_name&#42;>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true). By default, this subkey is set to 0 (false).  
  
-   A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.  
  
If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:  
  
-   "The job step requires a proxy account, however proxy matching is disabled on the target server."  
  
    To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.  
  
-   "Proxy not found."  
  
    To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.  
  
#### <a name="Permissions"></a>Permissions  
Permissions to execute this procedure default to members of the **sysadmin** fixed server role.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To make a target server  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)], and then expand that instance.  
  
2.  Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**. The **Target Server Wizard** guides you through the process of making a target server.  
  
3.  From the **Select a Master Server** page, select the master server that this target server will receive jobs from.  
  
    **Pick Server**  
    Connect to the master server.  
  
    **Description of this server**  
    Type a description for this target server. The target server uploads this description to the master server.  
  
4.  From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.  
  
    **Create a new login if necessary and assign it rights to the MSX**  
    Create a new login on the target server if the login specified does not already exist.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To make a target server  
  
1.  Connect to the [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  From the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**. This example enlists the current server into the AdventureWorks1 master server. The location for the current server is Building 21, Room 309, Rack 5.  
  
    ```  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
    For more information, see [sp_msx_enlist (Transact-SQL)](http://msdn.microsoft.com/en-us/ceb3b2bc-0cc4-48d8-9bdc-6a809556e35f).  
  
## See Also  
[Automated Administration Across an Enterprise](../../ssms/agent/automated-administration-across-an-enterprise.md)  
  
