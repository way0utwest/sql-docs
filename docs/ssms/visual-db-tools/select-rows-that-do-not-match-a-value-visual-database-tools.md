---
title: "Select Rows That Do Not Match a Value (Visual Database Tools) | Microsoft Docs"
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
  - "search conditions [SQL Server], rows not matching value"
  - "row not matching value [SQL Server]"
  - "NOT operator [Visual Database Tools]"
  - "search criteria [SQL Server], rows not matching value"
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Select Rows That Do Not Match a Value (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
To find rows that do not match a value, use the NOT operator.  
  
### To find rows that do not match a value  
  
1.  If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md).  
  
2.  Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.  
  
For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:  
  
```  
NOT LIKE 'A%'  
```  
  
## See Also  
[Rules for Entering Search Values (Visual Database Tools)](../../ssms/visual-db-tools/rules-for-entering-search-values-visual-database-tools.md)  
[Specify Search Criteria (Visual Database Tools)](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
  
