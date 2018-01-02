---
title: "Drivers | Microsoft Docs"
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
  - "ODBC architecture [ODBC], drivers"
  - "drivers [ODBC]"
  - "drivers [ODBC], about drivers"
ms.assetid: d6795d92-877e-44e1-b7d5-2ff2fd3989bd
caps.latest.revision: 7
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Drivers
*Drivers* are libraries that implement the functions in the ODBC API. Each is specific to a particular DBMS; for example, a driver for Oracle cannot directly access data in an Informix DBMS. Drivers expose the capabilities of the underlying DBMSs; they are not required to implement capabilities not supported by the DBMS. For example, if the underlying DBMS does not support outer joins, then neither should the driver. The only major exception to this is that drivers for DBMSs that do not have stand-alone database engines, such as Xbase, must implement a database engine that at least supports a minimal amount of SQL.  
  
 This section contains the following topics.  
  
-   [Driver Tasks](../../odbc/reference/driver-tasks.md)  
  
-   [Driver Architecture](../../odbc/reference/driver-architecture.md)  
  
## See Also  
 [Microsoft-Supplied ODBC Drivers](../../odbc/microsoft/microsoft-supplied-odbc-drivers.md)
