---
title: "Remove Joins (Visual Database Tools) | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-visual-db"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "removing joins"
  - "joins [SQL Server], removing"
  - "deleting joins"
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
caps.latest.revision: 3
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Remove Joins (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them. For example, you might remove a join that the [Query and View Designer](../../ssms/visual-db-tools/query-and-view-designer-tools-visual-database-tools.md) has been created automatically between two tables.  
  
> [!NOTE]  
> Removing a join from a query does not alter the underlying relationship in the database.  
  
If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables — that is, it becomes a CROSS JOIN.  
  
### To remove a join  
  
-   In the [Diagram pane](../../ssms/visual-db-tools/diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key. You can select and delete multiple join lines at one time.  
  
The Query and View Designer removes the join line and alters the statement in the [SQL pane](../../ssms/visual-db-tools/sql-pane-visual-database-tools.md).  
  
## See Also  
[Join Tables Automatically &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/join-tables-automatically-visual-database-tools.md)  
[Join Tables Manually &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/join-tables-manually-visual-database-tools.md)  
[Query with Joins &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/query-with-joins-visual-database-tools.md)  
  
