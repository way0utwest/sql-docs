---
title: "MSSQLSERVER_8621 | Microsoft Docs"
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
  - "8621 (Database Engine error)"
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_8621
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|8621|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|OPTIMIZER_STACK_OVERFLOW_ERR|  
|Message Text|The query processor ran out of stack space during query optimization. Please simplify the query.|  
  
## Explanation  
The size of the expanded query is the most likely cause of the error. The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.  
  
Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.  
  
## User Action  
Simplify the query by breaking the query into multiple queries along the largest dimension. First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.  Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.  
  
