---
title: "xp_revokelogin (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "06/10/2016"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "system-stored-procedures"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "xp_revokelogin"
  - "xp_revokelogin_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "xp_revokelogin"
ms.assetid: b3fa7678-dba4-4537-be94-5ae63ca11f81
caps.latest.revision: 25
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# xp_revokelogin (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Revokes access from a Windows group or user to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Use [DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md) instead.  
  
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
xp_revokelogin {[@loginame=] 'login'}  
```  
  
## Arguments  
 [ **@loginame =** ] **'***login***'**  
 Is the name of the Windows user or group from which to revoke access. *login* must include the domain name, for example **[ADVWKS\sylvester1]**. *login* is **sysname**, with no default.  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Remarks  
 Use DROP LOGIN instead.  
  
## Permissions  
 Requires ALTER ANY LOGIN permission on the server.  
  
## See Also  
 [sp_denylogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-denylogin-transact-sql.md)   
 [sp_grantlogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-grantlogin-transact-sql.md)   
 [sp_revokelogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-revokelogin-transact-sql.md)   
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [General Extended Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/general-extended-stored-procedures-transact-sql.md)   
 [xp_loginconfig &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/xp-loginconfig-transact-sql.md)   
 [xp_logininfo &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/xp-logininfo-transact-sql.md)  
  
  
