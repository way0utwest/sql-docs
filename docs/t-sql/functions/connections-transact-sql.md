---
title: "@@CONNECTIONS (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/18/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-database"
ms.service: ""
ms.component: "t-sql|functions"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "@@CONNECTIONS"
  - "@@CONNECTIONS_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "@@CONNECTIONS function"
  - "connections [SQL Server], number of"
  - "connections [SQL Server], attempted"
  - "number of connection attempts"
  - "attempted connections"
ms.assetid: c59836a8-443c-4b9a-8b96-8863ada97ac7
caps.latest.revision: 32
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# &#x40;&#x40;CONNECTIONS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Returns the number of attempted connections, either successful or unsuccessful since [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was last started.
  
![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## Syntax  
  
```sql
@@CONNECTIONS  
```  
  
## Return types
**integer**
  
## Remarks  
Connections are different from users. Applications, for example, can open multiple connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without the user observing the connections.
  
To display a report containing several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statistics, including connection attempts, run **sp_monitor**.
  
@@MAX_CONNECTIONS is the maximum number of connections allowed simultaneously to the server. @@CONNECTIONS is incremented with each login attempt, therefore @@CONNECTIONS can be greater than @@MAX_CONNECTIONS.
  
## Examples  
The following example shows returning the number of login attempts as of the current date and time.
  
```sql
SELECT GETDATE() AS 'Today''s Date and Time',   
@@CONNECTIONS AS 'Login Attempts';  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
  
Today's Date and Time  Login Attempts  
---------------------- --------------  
12/5/2006 10:32:45 AM  211023         
```  
  
## See also
[System Statistical Functions &#40;Transact-SQL&#41;](../../t-sql/functions/system-statistical-functions-transact-sql.md)  
[sp_monitor &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)
  
  
