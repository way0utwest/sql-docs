---
title: "UPDATE Statement Limitations | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "odbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UPDATE statement limitations [ODBC]"
  - "ODBC SQL grammar, UPDATE statement limitations"
ms.assetid: 14700aac-e135-4dc0-9138-4b01224461d5
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# UPDATE Statement Limitations
For the Paradox driver to update a table, the table must have a unique index (Paradox primary key). When you use the Paradox driver without implementing the Borland Database Engine, it is not possible to update a Paradox table.  
  
 Not supported by the Text driver.  
  
 When the Microsoft Excel driver is used, it is possible to update values, but a row cannot be deleted from a table based on a Microsoft Excel spreadsheet. As a result, the UPDATE statement is not considered officially supported by the Microsoft Excel driver. Only the INSERT statement is considered supported.
