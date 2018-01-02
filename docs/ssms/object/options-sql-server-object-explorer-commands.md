---
title: "Options (SQL Server Object Explorer - Commands) | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-objects"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Sql_Server_Object_Explorer.ObjectExplorerCommands"
ms.assetid: 0e5afdb3-488c-4ea9-9e38-d42085ec00b1
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Options (SQL Server Object Explorer - Commands)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
When you right-click a table or view in Object Explorer, the following two options for displaying rows in the table are presented:  
  
-   **Select Top 1000 Rows**  
  
    Creates a script in the Query Editor that selects the top 1000 rows.  
  
-   **Edit Top 200 Rows**  
  
    Opens the table in the Visual Database Tools with 200 rows populated.  
  
Use the **General Scripting Options** dialog box to change the number of rows that will be opened.  
  
## General Scripting Options  
**Value for Select Top <n> Audit record command**  
Specifies the number of audit rows to return. The default is 1000 rows  
  
**Value for Edit Top <n> Rows command**  
Specifies the number of rows to return when you are editing rows in a table. The default is 200 rows.  
  
**Value for Select Top <n> Rows command**  
Specifies the number of rows to be returned that is specified in the Query Editor script that is created. The default is 1000 rows.  
  
## See Also  
[SQL Server Audit (Database Engine)](http://msdn.microsoft.com/en-us/0c1fca2e-f22b-4fe8-806f-c87806664f00)  
  
