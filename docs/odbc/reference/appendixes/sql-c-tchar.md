---
title: "SQL_C_TCHAR | Microsoft Docs"
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
  - "sql_c_tchar [ODBC]"
  - "pseudo-type identifiers [ODBC], SQL_C_TCHAR"
  - "data types [ODBC], pseudo-type identifiers"
ms.assetid: 9e27c8bd-ee15-4ce9-b70a-34cf1bf16f4c
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQL_C_TCHAR
The SQL_C_TCHAR type identifier does not actually identify a data type; it is a macro that exists within the header file for Unicode conversion. It is replaced by SQL_C_CHAR or SQL_C_WCHAR depending on the setting of the UNICODE **#define**. It is useful for an application transferring character data that is compiled as both an ANSI and a Unicode application.
