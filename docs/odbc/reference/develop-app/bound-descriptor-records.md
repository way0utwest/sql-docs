---
title: "Bound Descriptor Records | Microsoft Docs"
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
  - "bound descriptor records [ODBC]"
  - "descriptors [ODBC], bound descriptor records"
ms.assetid: 55d09344-6682-40f6-b634-036b134ff650
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Bound Descriptor Records
When the application sets the SQL_DESC_DATA_PTR field of a descriptor record so that it no longer contains a null value, the record is said to be *bound*.  
  
 If the descriptor is an APD, each bound record constitutes a bound parameter. For input parameters, the application must bind a parameter for each dynamic parameter marker in the SQL statement before executing the statement. For output parameters, the application need not bind the parameter.  
  
 If the descriptor is an ARD, which describes a row of database data, each bound record constitutes a bound column.
