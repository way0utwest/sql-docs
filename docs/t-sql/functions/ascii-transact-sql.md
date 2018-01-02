---
title: "ASCII (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/24/2017"
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
  - "ASCII_TSQL"
  - "ASCII"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "ASCII function"
  - "characters [SQL Server], ASCII"
  - "code [SQL Server], ASCII"
  - "leftmost character of expression"
ms.assetid: 45c2044a-0593-4805-8bae-0fad4bde2e6b
caps.latest.revision: 37
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Active"
---
# ASCII (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

Returns the ASCII code value of the leftmost character of a character expression.
  
![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## Syntax  
  
```sql
ASCII ( character_expression )  
```  
  
## Arguments  
*character_expression*  
Is an [expression](../../t-sql/language-elements/expressions-transact-sql.md) of the type **char** or **varchar**.
  
## Return types
 **int**  
  
## Remarks
ASCII is an abbreviation for American Standard Code for Information Interchange. It is a character encoding standard used by computers. For a list of ASCII characters, see the **Printable characters** section of [ASCII](https://www.wikipedia.org/wiki/ASCII).

## Examples  
The following example assumes an ASCII character set and returns the `ASCII` value for 6 characters.
  
```sql
SELECT ASCII('A') AS A, ASCII('B') AS B,   
ASCII('a') AS a, ASCII('b') AS b,  
ASCII(1) AS [1], ASCII(2) AS [2];  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
A           B           a           b           1           2  
----------- ----------- ----------- ----------- ----------- -----------  
65          66          97          98          49          50  
```  
  
## See also
[String Functions &#40;Transact-SQL&#41;](../../t-sql/functions/string-functions-transact-sql.md)
  
  


