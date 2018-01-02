---
title: "SQLBindCol (Visual FoxPro ODBC Driver) | Microsoft Docs"
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
  - "SQLBindCol function [ODBC], Visual FoxPro ODBC Driver"
ms.assetid: 984d6605-39ba-4d33-ac94-22625bfa6107
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLBindCol (Visual FoxPro ODBC Driver)
> [!NOTE]  
>  This topic contains Visual FoxPro ODBC Driver-specific information. For general information about this function, see the appropriate topic under [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Support: Full  
  
 ODBC API Conformance: Core Level  
  
 Assigns storage space for a result column and specifies the type of the result. When [SQLFetch](../../odbc/microsoft/sqlfetch-visual-foxpro-odbc-driver.md) or [SQLExtendedFetch](../../odbc/microsoft/sqlextendedfetch-visual-foxpro-odbc-driver.md) is called, the driver places the data for all bound columns in the assigned locations. See [SQLGetTypeInfo](../../odbc/microsoft/sqlgettypeinfo-visual-foxpro-odbc-driver.md) for the mapping between ODBC and Visual FoxPro data types.  
  
 For more information, see [SQLBindCol](../../odbc/reference/syntax/sqlbindcol-function.md) in the *ODBC Programmer's Reference*.
