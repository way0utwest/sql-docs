---
title: "SQLExtendedFetch (Cursor Library) | Microsoft Docs"
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
  - "SQLExtendedFetch function [ODBC], Cursor Library"
ms.assetid: 06fbf06f-127b-475c-b636-7b784918475d
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLExtendedFetch (Cursor Library)
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 This topic discusses the use of the **SQLExtendedFetch** function in the cursor library. For general information about **SQLExtendedFetch**, see [SQLExtendedFetch Function](../../../odbc/reference/syntax/sqlextendedfetch-function.md).  
  
 The cursor library implements **SQLExtendedFetch** by repeatedly calling **SQLFetch** in the driver.  
  
 The cursor library supports calling **SQLExtendedFetch** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.  
  
 When the cursor library is used, calls to **SQLExtendedFetch** cannot be mixed with calls to either **SQLFetchScroll** or **SQLFetch**.
