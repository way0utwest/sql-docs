---
title: "Jet: Date, Time, and Timestamp Literals | Microsoft Docs"
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
  - "literals [ODBC], SQL grammar"
  - "SQL grammar [ODBC], literals"
  - "date literals [ODBC]"
  - "timestamp literals [ODBC]"
  - "time literals [ODBC]"
ms.assetid: 37db1ae1-ca4e-4cd8-9b47-7f1a38e7fcad
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Jet: Date, Time, and Timestamp Literals
For maximum interoperability, applications should pass date literals in the ODBC canonical format using escape-clause syntax:  
  
-   For date literals, {d '*value*'}, where *valu*e is in the form "yyyy-mm-dd"  
  
-   For time literals, {t '*value*'}, where *valu*e is in the form "hh:mm:ss"  
  
 For timestamp literals {ts '*value*'}, where *valu*e is in the form "yyyy-mm-dd hh:mm:ss[.f...]".
