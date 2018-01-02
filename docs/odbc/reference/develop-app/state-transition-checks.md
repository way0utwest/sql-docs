---
title: "State Transition Checks | Microsoft Docs"
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
  - "state transition checks [ODBC]"
  - "driver manager [ODBC], error checking"
ms.assetid: 0706db7d-e125-4845-a13a-7fe4308f7360
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# State Transition Checks
The Driver Manager checks that the state of the environment, connection, or statement is appropriate for the function being called. For example, a connection must be in an allocated state when **SQLConnect** is called; a statement must be in a prepared state when **SQLExecute** is called. The Driver Manager returns SQL_ERROR for state transition errors.
