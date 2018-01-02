---
title: "SET OFFSETS (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "06/10/2016"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "t-sql|statements"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SET_OFFSETS_TSQL"
  - "OFFSETS_TSQL"
  - "SET OFFSETS"
  - "OFFSETS"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "position relative to start of statement [SQL Server]"
  - "OFFSETS option"
  - "offsets [SQL Server]"
  - "SET OFFSETS statement"
ms.assetid: c7bcc697-0930-4630-acae-d8ccbfa4414c
caps.latest.revision: 25
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# SET OFFSETS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Returns the offset (position relative to the start of a statement) of specified keywords in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to DB-Library applications.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
 
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
SET OFFSETS keyword_list { ON | OFF }  
```  
  
## Arguments  
 *keyword_list*  
 Is a comma-separated list of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs including SELECT, FROM, ORDER, TABLE, PROCEDURE, STATEMENT, PARAM, and EXECUTE.  
  
## Remarks  
 SET OFFSETS is used only in DB-Library applications.  
  
 The setting of SET OFFSETS is set at parse time and not at execute time or run time. Setting at parse time means that if the SET statement is present in the batch or stored procedure, the setting takes effect, regardless of whether code execution actually reaches that point; and the SET statement takes effect before any statements are executed. For example, even if the set statement is in an IF...ELSE statement block that is never reached during execution, the SET statement still takes effect because the IF...ELSE statement block is parsed.  
  
 If SET OFFSETS is set in a stored procedure, the value of SET OFFSETS is restored after control is returned from the stored procedure. Therefore, a SET OFFSETS statement specified in dynamic SQL does not have any effect on any statements following the dynamic SQL statement.  
  
 SET PARSEONLY returns offsets if the OFFSETS option is ON and no errors occur.  
  
## Permissions  
 Requires membership in the **public** role.  
  
## See Also  
 [SET Statements &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)   
 [SET PARSEONLY &#40;Transact-SQL&#41;](../../t-sql/statements/set-parseonly-transact-sql.md)  
  
  
