---
title: "Driver Manager Error and Warning Checks | Microsoft Docs"
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
  - "diagnostic information [ODBC], driver manager error checking"
  - "driver manager [ODBC], error checking"
ms.assetid: eeb5ab3f-987d-4f30-87d2-7425a81ad1d7
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Driver Manager Error and Warning Checks
The Driver Manager completely or partially implements a number of functions and therefore checks for all or some of the errors and warnings in those functions.  
  
-   The Driver Manager implements **SQLDataSources** and **SQLDrivers** and checks for all errors and warnings in these functions.  
  
-   The Driver Manager checks whether a driver implements **SQLGetFunctions**. If the driver does not implement **SQLGetFunctions**, the Driver Manager implements and checks for all errors and warnings in it.  
  
-   The Driver Manager partially implements **SQLAllocHandle**, **SQLConnect**, **SQLDriverConnect**, **SQLBrowseConnect**, **SQLFreeHandle**, **SQLGetDiagRec**, and **SQLGetDiagField** and checks for some errors in these functions. It may return the same errors as the driver for some of these functions because both perform similar operations. For example, the Driver Manager or driver may return SQLSTATE IM008 (Dialog failed) if either one is unable to display a login dialog box for **SQLDriverConnect**.
