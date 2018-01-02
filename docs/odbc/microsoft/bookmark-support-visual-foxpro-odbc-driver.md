---
title: "Bookmark Support (Visual FoxPro ODBC Driver) | Microsoft Docs"
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
  - "FoxPro ODBC driver [ODBC], bookmarks"
  - "Visual FoxPro ODBC driver [ODBC], bookmarks"
  - "bookmarks [ODBC]"
ms.assetid: feb7ec20-3e0c-4a47-8feb-7dd9f23efdf6
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Bookmark Support (Visual FoxPro ODBC Driver)
The Visual FoxPro ODBC Driver supports simple bookmarks. When you call [SQLGetInfo](../../odbc/microsoft/sqlgetinfo-visual-foxpro-odbc-driver.md) with the SQL_BOOKMARK_PERSISTENCE *InfoType*, the return value is SQL_BP_SCROLL.  
  
 For more information about bookmarks, see [Bookmarks (ODBC)](../../odbc/reference/develop-app/bookmarks-odbc.md).
