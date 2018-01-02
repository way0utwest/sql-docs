---
title: "MSSQLSERVER_8710 | Microsoft Docs"
ms.custom: ""
ms.date: "04/04/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "errors-events"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
helpviewer_keywords: 
  - "8710 (Database Engine error)"
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_8710
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|MSSQLSERVER|  
|Event ID|8710|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|QUERY2_CUBE_ILLEGAL_AGG_FUNC|  
|Message Text|Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates. To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.|  
  
## Explanation  
An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.  
  
## User Action  
To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.  
  
