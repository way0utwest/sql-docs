---
title: "CREATE INDEX Statement | Microsoft Docs"
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
  - "CREATE INDEX [ODBC]"
  - "SQL grammar [ODBC], create index"
ms.assetid: 69438247-eef3-44c5-bef2-acef4e146f41
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# CREATE INDEX Statement
The syntax of the CREATE INDEX statement is:  
  
 CREATE [UNIQUE] INDEX *index-name* ON *table-name* (*column-identifier* [ASC][DESC][, *column-identifier* [ASC][DESC]...]) WITH \<*index option list*>  
  
 where \<*index option list*> can be: PRIMARY &#124; DISALLOW NULL &#124; IGNORE NULL  
  
 Only the Microsoft Access driver uses the DISALLOW NULL and IGNORE NULL index options. The dBASE and Paradox drivers accept the syntax, but ignore the presence of either option.  
  
 When the Paradox driver is used, the CREATE INDEX statement creates Paradox primary key files and secondary files.  
  
 This statement is not supported by the Microsoft Excel or Text drivers.
