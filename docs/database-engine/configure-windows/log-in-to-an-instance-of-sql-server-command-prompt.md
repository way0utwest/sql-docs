---
title: "Log In to an Instance of SQL Server (Command Prompt) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "configure-windows"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "logins [SQL Server], named instance of SQL Server"
  - "log ins [SQL Server]"
  - "logins [SQL Server], default instance of SQL Server"
  - "command prompt [SQL Server], logins"
  - "logging in [SQL Server]"
ms.assetid: f67c11e3-c519-40c9-82c1-07efa9d9985e
caps.latest.revision: 26
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Log In to an Instance of SQL Server (Command Prompt)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  This topic describes how to test connectivity to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the **sqlcmd** utility.  
  
##  <a name="SSMSProcedure"></a>  
  
#### To log in to the default instance of SQL Server  
  
1.  From a command prompt, enter the following command to connect by using Windows Authentication:  
  
    ```  
    sqlcmd [ /E ] [ /S servername ]  
  
    ```  
  
#### To log in to a named instance of SQL Server  
  
1.  From a command prompt, enter the following command to connect by using Windows Authentication:  
  
    ```  
    sqlcmd [ /E ] /S servername\instancename  
  
    ```  
  
## See Also  
 [sqlcmd Utility](../../tools/sqlcmd-utility.md)   
 [osql Utility](../../tools/osql-utility.md)  
  
  
