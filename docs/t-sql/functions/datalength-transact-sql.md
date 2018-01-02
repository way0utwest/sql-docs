---
title: "DATALENGTH (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/29/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "t-sql|functions"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "DATALENGTH_TSQL"
  - "DATALENGTH"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "number of bytes representing expression"
  - "data types [SQL Server], length"
  - "DATALENGTH function"
  - "expressions [SQL Server], length"
  - "lengths [SQL Server], data"
ms.assetid: 00f377f1-cc3e-4eac-be47-b3e3f80267c9
caps.latest.revision: 31
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Active"
---
# DATALENGTH (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

Returns the number of bytes used to represent any expression.
  
![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## Syntax  
  
```sql
DATALENGTH ( expression )   
```  
  
## Arguments  
*expression*  
Is an [expression](../../t-sql/language-elements/expressions-transact-sql.md) of any data type.
  
## Return types
**bigint** if *expression* is of the **varchar(max)**, **nvarchar(max)** or **varbinary(max)** data types; otherwise **int**.
  
## Remarks  
DATALENGTH is especially useful with **varchar**, **varbinary**, **text**, **image**, **nvarchar**, and **ntext** data types because these data types can store variable-length data.
  
The DATALENGTH of NULL is NULL.
  
> [!NOTE]  
>  Compatibility levels can affect return values. For more information about compatibility levels, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md).  
  
## Examples  
The following example finds the length of the `Name` column in the `Product` table.
  
```sql
-- Uses AdventureWorks  
  
SELECT length = DATALENGTH(EnglishProductName), EnglishProductName  
FROM dbo.DimProduct  
ORDER BY EnglishProductName;  
GO  
```  
  
## See also
[LEN &#40;Transact-SQL&#41;](../../t-sql/functions/len-transact-sql.md)  
[CAST and CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[Data Types &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)  
[System Functions &#40;Transact-SQL&#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)
  
  

