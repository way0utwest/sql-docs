---
title: "MinDbCompatibilityLevel (geometry Data Type) | Microsoft Docs"
ms.custom: ""
ms.date: "08/03/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "t-sql|spatial-geography"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "MinDbCompatibilityLevel method (geometry)"
ms.assetid: c848b974-8ccb-4c5c-a7eb-b019a9538d99
caps.latest.revision: 17
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# MinDbCompatibilityLevel (geometry Data Type)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

Returns the minimum database compatibility level that recognizes the **geometry** data type instance.
  
## Syntax  
  
```  
  
.MinDbCompatibilityLevel ( )  
```  
  
## Return Types  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] return type: **int**  
  
 CLR return type: **int**  
  
## Remarks  
 Use `MinDbCompatibilityLevel()` to test a spatial object for compatibility before changing the compatibility level on a database.  
  
## Examples  
  
### A. Testing CircularString type for compatibility with compatibility level 110  
 The following example tests a `CircularString` instance for compatibility with an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
```
 DECLARE @g geometry = 'CIRCULARSTRING(3 4, 8 9, 5 6)'; 
 IF @g.MinDbCompatibilityLevel() <= 110 
 BEGIN 
 SELECT @g.ToString(); 
 END
 ```  
  
### B. Testing LineString type for compatibility with compatibility level 100  
 The following example tests a `LineString` instance for compatibility with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:  
  
```
 DECLARE @g geometry = 'LINESTRING(3 4, 8 9, 5 6)'; 
 IF @g.MinDbCompatibilityLevel() <= 100 
 BEGIN 
 SELECT @g.ToString(); 
 END
``` 
  
## See Also  
 [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md)  
  
  

