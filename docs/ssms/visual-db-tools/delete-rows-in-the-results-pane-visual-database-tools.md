---
title: "Delete Rows in the Results Pane (Visual Database Tools) | Microsoft Docs"
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
  - "View Designer, Results pane"
  - "removing rows"
  - "row removal [SQL Server], Visual Database Tools Results pane"
  - "row deletions [SQL Server], Visual Database Tools Results pane"
  - "Query Designer [SQL Server], Results pane"
  - "deleting rows"
  - "Results pane"
ms.assetid: a1147905-fe4a-4fac-b576-a17622477e66
caps.latest.revision: 3
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Delete Rows in the Results Pane (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Delete rows in the Results pane if you want to delete records in the database. If you want to delete all of the rows you can use a Delete query. For more information see [Create Delete Queries &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/create-delete-queries-visual-database-tools.md). If you only want to remove rows from the Results pane, change the criteria for the query. For more information see [Specify Search Criteria &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md).  
  
### To delete a row or rows  
  
1.  Select the box to the left of the row or rows you want to delete in the Results pane.  
  
2.  Press DELETE.  
  
3.  In the message box asking for confirmation, click **Yes**.  
  
> [!CAUTION]  
> Rows you delete in this way are permanently removed from the database and cannot be recalled.  
  
> [!NOTE]  
> If any of the selected rows can't be deleted from the database, none of them will be deleted and you will receive a message telling you which rows can't be deleted.  
  
## See Also  
[Create Delete Queries &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/create-delete-queries-visual-database-tools.md)  
[Specify Search Criteria &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
  
