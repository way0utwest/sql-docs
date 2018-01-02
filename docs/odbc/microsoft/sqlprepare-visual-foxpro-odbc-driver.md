---
title: "SQLPrepare (Visual FoxPro ODBC Driver) | Microsoft Docs"
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
  - "SQLPrepare function [ODBC], Visual FoxPro ODBC Driver"
ms.assetid: 0c4cb5a4-9729-4b2e-a0c6-52027b92e8fc
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLPrepare (Visual FoxPro ODBC Driver)
> [!NOTE]  
>  This topic contains Visual FoxPro ODBC Driver-specific information. For general information about this function, see the appropriate topic under [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Support: Full  
  
 ODBC API Conformance: Core Level  
  
 Prepares an SQL statement by planning how to optimize and execute the statement. The SQL statement is compiled for execution by [SQLExecDirect](../../odbc/microsoft/sqlexecdirect-visual-foxpro-odbc-driver.md).  
  
 If your table, view, or field names contain spaces, enclose the names in back quote (`) marks. For example, if your database contains a table named My Table and the field My Field, enclose each element of the identifier as follows:  
  
```  
SELECT * FROM `My Table`.`My Field`  
```  
  
 For more information, see [SQLPrepare](../../odbc/reference/syntax/sqlprepare-function.md) in the *ODBC Programmer's Reference*.
