---
title: "Execution Characteristics of Extended Stored Procedures | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "extended-stored-procedures"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "extended stored procedures [SQL Server], executing"
  - "executing extended stored procedures [SQL Server]"
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
caps.latest.revision: 33
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Execution Characteristics of Extended Stored Procedures
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Use CLR Integration instead.  
  
 The execution of an extended stored procedure has these characteristics:  
  
-   The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
-   The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
-   The thread associated with the execution of the extended stored procedure is the same one used for the client connection.  
  
    > [!IMPORTANT]  
    >  Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.  
  
-  
  
 After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).  
  
 The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## Parameters  
 @ *retval*  
 Is a return value.  
  
 @ *param1*  
 Is an input parameter.  
  
 @ *param2*  
 Is an input/output parameter.  
  
> [!CAUTION]  
>  Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality. However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning. Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas. As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. These procedures should be thoroughly tested before they are installed.  
  
## See Also  
 [Programming Extended Stored Procedures](../../relational-databases/extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)   
 [Querying Extended Stored Procedures Installed in SQL Server](../../relational-databases/extended-stored-procedures-programming/querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
