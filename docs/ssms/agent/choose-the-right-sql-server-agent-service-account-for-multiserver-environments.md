---
title: "Choose the Agent Service Account for Multiserver Environments | Microsoft Docs"
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
  - "SQL Server Agent, service accounts"
  - "multiserver environments [SQL Server], SQL Server Agent service account behavior"
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Choose the Right SQL Server Agent Service Account for Multiserver Environments
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent service can affect the behavior of a multiserver environment, as follows:  
  
-   If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail. If it does, the following error message is returned:  
  
    "The enlistment operation failed."  
  
    Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent services to resolve this issue.  
  
-   When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer. If you use this configuration, the following message is returned when you enlist target servers to a master server:  
  
    "Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."  
  
    You can ignore this informational message. The enlistment operation should complete successfully.  
  
For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](../../ssms/agent/select-an-account-for-the-sql-server-agent-service.md).  
  
