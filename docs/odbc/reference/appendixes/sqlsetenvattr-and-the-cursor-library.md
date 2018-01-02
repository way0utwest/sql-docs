---
title: "SQLSetEnvAttr and the Cursor Library | Microsoft Docs"
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
  - "SQLSetEnvAttr function [ODBC], Cursor Library"
ms.assetid: 59cc8eae-09ae-4796-869a-c5806488ae83
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLSetEnvAttr and the Cursor Library
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 This topic discusses the use of the **SQLSetEnvAttr** function with the cursor library. For general information about **SQLSetEnvAttr**, see [SQLSetEnvAttr Function](../../../odbc/reference/syntax/sqlsetenvattr-function.md).  
  
 The cursor library is unaffected by the setting of the SQL_ATTR_ODBC_VERSION environment attribute, regardless of the application version or driver version.
