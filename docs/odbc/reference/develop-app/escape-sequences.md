---
title: "Escape Sequences | Microsoft Docs"
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
  - "SQL statements [ODBC], interoperability"
  - "escape sequences [ODBC], determining if supported"
  - "interoperability of SQL statements [ODBC], escape sequences"
ms.assetid: 5913abfa-d280-43e4-a2f1-05a924388bf9
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Escape Sequences
ODBC defines escape sequences containing standard grammar for date, time, timestamp, and datetime interval literals, scalar function calls, **LIKE** predicate escape characters, outer joins, and procedure calls. Interoperable applications should use these sequences whenever possible.  
  
 To determine if a driver supports the escape sequences for date, time, timestamp, or datetime interval literals, an application calls **SQLGetTypeInfo**. If the data source supports a date, time, timestamp, or datetime interval data type, it must also support the corresponding escape sequence. To determine whether the other escape sequences are supported, an application calls **SQLGetInfo**.  
  
 For more information, see [Escape Sequences in ODBC](../../../odbc/reference/develop-app/escape-sequences-in-odbc.md), later in this section.
