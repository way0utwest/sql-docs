---
title: "ODBC Functions Not Executed by the Cursor Library | Microsoft Docs"
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
  - "cursor library [ODBC], functions"
  - "functions [ODBC], cursor library"
  - "ODBC functions [ODBC], cursor library"
  - "ODBC cursor library [ODBC], functions"
ms.assetid: f2941522-75eb-4db9-9468-4800b884dac2
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ODBC Functions Not Executed by the Cursor Library
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 The cursor library does not execute the following functions. When an application calls one of these functions, the Driver Manager invokes the driver, not the cursor library.  
  
|||  
|-|-|  
|**SQLFetch**|**SQLGetEnvAttr**|  
|**SQLGetConnectAttr**|**SQLSetDescRec**|  
|**SQLGetDiagField**|**SQLSetEnvAttr**|  
|**SQLGetDiagRec**||
