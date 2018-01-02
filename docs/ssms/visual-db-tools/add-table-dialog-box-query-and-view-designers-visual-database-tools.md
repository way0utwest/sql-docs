---
title: "Add Table Dialog Box (Query and View Designers) (Visual DB tools) | Microsoft Docs"
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
  - "vdt.dlgbox.query.addtable"
  - "vdtsql.chm:65565"
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Add Table Dialog Box (Query and View Designers) (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.  
  
> [!NOTE]  
> If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](http://msdn.microsoft.com/en-us/f1745145-182d-4301-a334-18f799d361d1) or SQL Server Management Objects (SMO). When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table. You cannot drop published objects, therefore the schema change will fail.  
  
## Options  
**Tables**  
Lists the tables you can add to the **Diagram** pane. To add a table, select it and click **Add**. To add several tables at once, select them and click **Add**.  
  
**Views**  
Lists the views you can add to the **Diagram** pane. To add a view, select it and click **Add**. To add several views at once, select them and click **Add**.  
  
**Functions**  
Lists the user-defined functions you can add to the **Diagram** pane. To add a function, select it and click **Add**. To add several functions at once, select them and click **Add**.  
  
**Synonyms**  
Lists the synonyms you can add to the **Diagram** pane. To add a synonym, select it and click **Add**. To add several synonyms at once, select them and click **Add**.  
  
**Refresh**  
Update the list to include any changes made to the database since the list was last retrieved.  
  
**Add**  
Add the selected item or items.  
  
## See Also  
[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
