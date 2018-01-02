---
title: "DROP INDEX Statement | Microsoft Docs"
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
  - "DROP INDEX [ODBC]"
  - "SQL grammar [ODBC], DROP INDEX"
ms.assetid: cd0ff767-9254-413b-bd1a-bed26c6774f5
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# DROP INDEX Statement
When the Microsoft Access, dBASE, or Paradox driver is used, the syntax of the DROP INDEX statement is "DROP INDEX a on b" where "a" is the name of the index and "b" is the name of the table (not DROP INDEX *index-name*).  
  
 When the Paradox driver is used, the DROP INDEX statement deletes Paradox secondary index files.  
  
 The DROP INDEX statement is not supported for the Microsoft Excel or Text drivers.
