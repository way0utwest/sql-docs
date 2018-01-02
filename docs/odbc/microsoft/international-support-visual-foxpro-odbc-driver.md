---
title: "International Support (Visual FoxPro ODBC Driver) | Microsoft Docs"
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
  - "double-byte character sets [ODBC]"
  - "FoxPro ODBC driver [ODBC], international support"
  - "DBCS [ODBC]"
  - "international support [ODBC]"
  - "sort order [ODBC]"
  - "collating sequences [ODBC]"
  - "Visual FoxPro ODBC driver [ODBC], international support"
ms.assetid: cd3fab32-13f1-4a86-abc4-5e18667669fc
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# International Support (Visual FoxPro ODBC Driver)
The Microsoft Visual FoxPro ODBC Driver supports:  
  
-   Double-byte character sets (DBCS)  
  
-   Multiple collating sequences  
  
 A collating sequence defines the *sort order* for data stored in a Visual FoxPro table or database. By default, the driver is configured to use the collating sequences that support the language version of your operating system.  
  
 For a list of supported collating sequences, see [SET COLLATE](../../odbc/microsoft/set-collate-command.md).  
  
## locale  
 The set of information that corresponds to a given language and country/region. A locale indicates specific settings such as decimal separators, date and time formats, and character-sorting order.  
  
## sort order  
 Sort orders incorporate the sorting rules of different *locale*s, allowing you to sort data in those languages correctly. In Visual FoxPro, the current sort order determines the results of character expression comparisons and the order in which the records appear in indexed or sorted tables.
