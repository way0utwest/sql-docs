---
title: "SQLBindParameter (Cursor Library) | Microsoft Docs"
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
  - "SQLBindParameter function [ODBC], Cursor Library"
ms.assetid: 04c53e4c-cd1d-40b2-9997-684ebe43499f
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLBindParameter (Cursor Library)
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 This topic discusses the use of the **SQLBindParameter** function in the cursor library. For general information about **SQLBindParameter**, see [SQLBindParameter Function](../../../odbc/reference/syntax/sqlbindparameter-function.md).  
  
 An application can call **SQLBindParameter** to rebind parameters, as long as the C data type, column size, and decimal digits of the bound column remain the same.  
  
 The cursor library supports setting the SQL_ATTR_ROW_BIND_OFFSET_PTR statement attribute to use bind offsets. (**SQLBindParameter** does not have to be called for this rebinding to occur.)  
  
 The cursor library supports binding data-at-execution parameters.
