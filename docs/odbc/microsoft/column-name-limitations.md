---
title: "Column Name Limitations | Microsoft Docs"
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
  - "desktop database drivers [ODBC], column names"
  - "ODBC desktop database drivers [ODBC], column names"
ms.assetid: 5a339f61-c52f-40ad-8deb-d785f72753d4
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Column Name Limitations
Column names can contain any valid characters (for example, spaces). If column names contain any characters except letters, numbers, and underscores, the name must be delimited by enclosing it in back quotes (`).  
  
 When the Microsoft Access or Microsoft Excel driver is used, column names are limited to 64 characters, and longer names generate an error. When the Paradox driver is used, the maximum column name is 25 characters. When the Text driver is used, the maximum column name is 64 characters, and longer names are truncated.  
  
 When the dBASE driver is used, characters with an ASCII value greater than 127 are converted to underscores.  
  
 When the Microsoft Excel driver is used, if column names are present, they must be in the first row. A name that in Microsoft Excel would use the "!" character must be enclosed in back quotes (`). The "!" character is converted to the "$" character, because the "!" character is not legal in an ODBC name, even when the name is enclosed in back quotes. All other valid Microsoft Excel characters (except the pipe character (&#124;)) can be used in a column name, including spaces. A delimited identifier must be used for a Microsoft Excel column name to include a space. Unspecified column names will be replaced with driver-generated names, for example, "Col1" for the first column.  
  
 The pipe character (&#124;) cannot be used in a column name, whether the name is enclosed in back quotes or not.  
  
 When the Text driver is used, the driver provides a default name if a column name is not specified. For example, the driver calls the first column F1, the second column F2, and so on.
