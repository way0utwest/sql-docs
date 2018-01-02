---
title: "Calling SQLSetPos to Insert Data | Microsoft Docs"
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
  - "compatibility [ODBC], SQLSetPos"
  - "SQLSetPos function [ODBC], inserting data"
  - "backward compatibility [ODBC], SqlSetPos"
ms.assetid: 03e5c4d0-2bb3-4649-9781-89cab73f78eb
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Calling SQLSetPos to Insert Data
When an ODBC 2.*x* application working with an ODBC 3*.x* driver calls **SQLSetPos** with an *Operation* argument of SQL_ADD, the Driver Manager does not map this call to **SQLBulkOperations**. If an ODBC 3*.x* driver should work with an application that calls **SQLSetPos** with SQL_ADD, the driver should support that operation.  
  
 One major difference in behavior when **SQLSetPos** is called with SQL_ADD occurs when it is called in state S6. In ODBC 2.*x*, the driver returned S1010 when **SQLSetPos** was called with SQL_ADD in state S6 (after the cursor has been positioned with **SQLFetch**). In ODBC 3*.x*, **SQLBulkOperations** with an *Operation* of SQL_ADD can be called in state S6. A second major difference in behavior is that **SQLBulkOperations** with an *Operation* of SQL_ADD can be called in state S5, while **SQLSetPos** with an **Operation** of SQL_ADD cannot. For the statement transitions that can occur for the same call in ODBC 3*.x*, see [Appendix B: ODBC State Transition Tables](../../../odbc/reference/appendixes/appendix-b-odbc-state-transition-tables.md).
