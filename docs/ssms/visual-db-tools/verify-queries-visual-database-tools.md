---
title: "Verify Queries (Visual Database Tools) | Microsoft Docs"
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
f1_keywords: 
  - "vdtsql.chm:100644"
helpviewer_keywords: 
  - "verifying queries"
  - "queries [SQL Server], verifying"
  - "checking queries"
ms.assetid: 1382c0c0-46dc-45f9-ab38-9bba1d347eea
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Verify Queries (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
To avoid problems, you can check the query you have built to ensure its syntax is correct. This option is especially useful when you enter statements in the [SQL pane](../../ssms/visual-db-tools/sql-pane-visual-database-tools.md).  
  
Some notes to keep in mind about verifying queries:  
  
-   A statement can be valid, and therefore be verified successfully, even if it cannot be represented in the **Diagram Pane** and **Criteria Pane**.  
  
-   SQL Verification can detect some, but not all SQL errors. If a query contains an error not detected during SQL verification, the database will detect the error when you run the query.  
  
-   Queries that contain parameters cannot be verified.  
  
### To verify an SQL statement  
  
-   Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.  
  
## See Also  
[Run Queries &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/run-queries-visual-database-tools.md)  
[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/perform-basic-operations-with-queries-visual-database-tools.md)  
  
