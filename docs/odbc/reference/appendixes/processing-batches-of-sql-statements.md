---
title: "Processing Batches of SQL Statements | Microsoft Docs"
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
  - "ODBC cursor library [ODBC], batches"
  - "ODBC cursor library [ODBC], statement processing"
  - "cursor library [ODBC], batches"
  - "SQL statements [ODBC], cursor library"
  - "cursor library [ODBC], statement processing"
  - "SQL statements [ODBC], batches"
  - "batches [ODBC], processing batches of SQL statements"
ms.assetid: 04b93ef9-11de-47a3-8bd8-ba963c42f182
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Processing Batches of SQL Statements
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 The cursor library does not support batches of SQL statements, including SQL statements for which the SQL_ATTR_PARAMSET_SIZE statement attribute is greater than 1. If an application submits a batch of SQL statements to the cursor library, the results are undefined.
