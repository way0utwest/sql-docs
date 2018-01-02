---
title: "Setting the Date Format on Connection | Microsoft Docs"
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
  - "date formats [ODBC]"
  - "ODBC driver for Oracle [ODBC], date formats"
ms.assetid: ba0d5123-db52-448b-8e19-b7647ce4b361
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Setting the Date Format on Connection
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Instead, use the ODBC driver provided by Oracle.  
  
 The new version of the Microsoft ODBC Driver for Oracle does not automatically set the date format for Oracle date fields. Previously when the driver connected, it used `ALTER SESSION SET NLS_DATE_FORMAT ='YYYY-MM-DD HH:MI:SS'`.  
  
 To set the date format, call ALTER SESSION SET and then perform the insert. For example:  
  
```  
conn.Execute "ALTER SESSION SET NLS_DATE_FORMAT = 'YYYY-MM-DD HH:MI:SS' "  
sSql = "INSERT INTO DATETEST VALUES (24,'1988-12-01 10:23:03')"  
conn.Execute sSql  
```
