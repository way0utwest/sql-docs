---
title: "Modify a SQL Server Agent Proxy | Microsoft Docs"
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
  - "proxies [SQL Server Agent], modifying"
  - "modifying SQL Server Agent proxy"
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Modify a SQL Server Agent Proxy
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] or [!INCLUDE[tsql](../../includes/tsql_md.md)].  
  
**In This Topic**  
  
-   **Before you begin:**  
  
    [Limitations and Restrictions](#Restrictions)  
  
    [Security](#Security)  
  
-   **To modify a SQL Server Agent proxy, using:**  
  
    [SQL Server Management Studio](#SSMSProcedure)  
  
    [Transact-SQL](#TsqlProcedure)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent proxies use credentials to store information about Windows user accounts. The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] is running.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs. If the proxy no longer has access to the subsystem, the job step fails. Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.  
  
-   If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent proxy  
  
1.  In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent proxy account that you want to modify.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Click the plus sign to expand the **Proxies** folder.  
  
4.  Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).  
  
5.  Right-click the proxy account you want to modify and select **Properties**.  
  
6.  In the *proxy_name***Proxy Account Properties** dialog box, make changes to the proxy account as necessary. For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).  
  
7.  When finished, click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent proxy  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
For more information, see [sp_update_proxy (Transact-SQL)](http://msdn.microsoft.com/en-us/864fd0e6-9d61-4f07-92ef-145318d2f881).  
  
