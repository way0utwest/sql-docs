---
title: "xp_sprintf (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "system-stored-procedures"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "xp_sprintf_TSQL"
  - "xp_sprintf"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "xp_sprintf"
ms.assetid: 1eedd65c-03cc-4eab-b76e-04684fdfec52
caps.latest.revision: 33
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# xp_sprintf (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Formats and stores a series of characters and values in the string output parameter. Each format argument is replaced with the corresponding argument.  
  
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
xp_sprintf { string OUTPUT , format }  
     [ , argument [ ,...n ] ]  
```  
  
## Arguments  
 *string*  
 Is a **varchar** variable that receives the output.  
  
 OUTPUT  
 When specified, puts the value of the variable in the output parameter.  
  
 *format*  
 Is a format character string with placeholders for *argument* values, similar to that supported by the C-language **sprintf** function. Currently, only the %s format argument is supported.  
  
 *argument*  
 Is a character string that represents the value of the corresponding format argument.  
  
 *n*  
 Is a placeholder that indicates that a maximum of 50 arguments can be specified.  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Result Sets  
 **xp_sprintf** returns the following message:  
  
 `The command(s) completed successfully.`  
  
## Permissions  
 Requires membership in the **public** role.  
  
## See Also  
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [General Extended Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/general-extended-stored-procedures-transact-sql.md)   
 [xp_sscanf &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/xp-sscanf-transact-sql.md)  
  
  
