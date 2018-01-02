---
title: "SQLProcedureColumns (Access Driver) | Microsoft Docs"
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
  - "Access driver [ODBC], SQLProcedureColumns"
  - "SQLProcedureColumns function [ODBC], Access Driver"
ms.assetid: 34fee995-5848-4ecb-bda0-fc362a77b2d9
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLProcedureColumns (Access Driver)
> [!NOTE]  
>  This topic provides Access Driver-specific information. For general information about this function, see the appropriate topic under [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Application developers should look for driver-defined columns starting at the end of the result set and proceeding backward.  
  
|Column|Comments|  
|------------|--------------|  
|COLUMN_TYPE|SQL_PARAM_INPUT or SQL_RESULT_COL|  
|ORDINAL|This is a driver-specific column that is returned at the end of the result set. The SQL type of the column is an integer.|
