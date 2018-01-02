---
title: "Interoperability | Microsoft Docs"
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
  - "interoperability [ODBC]"
  - "interoperability [ODBC], about interoperability"
ms.assetid: 43b7c849-9d59-4002-9977-9e2c8730b859
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Interoperability
*Interoperability* is the ability of a single application to operate with many different DBMSs. The need to write generic, interoperable applications was one of the major factors leading to the development of ODBC. However, interoperability is not a simple path followed from "not interoperable" to "completely interoperable." The path has many branches, and each requires trade-offs among features, speed, code complexity, and development time.  
  
 The process of writing an interoperable application follows several steps:  
  
1.  Deciding whether the application will use ODBC.  
  
2.  Choosing a level of interoperability and deciding which trade-offs are necessary to reach that level.  
  
3.  Writing interoperable code and testing it as fully as possible.  
  
 It should be noted that interoperability is primarily the domain of the application writer. Drivers are designed to work with a single DBMS and, by definition, are not interoperable. They play a role in interoperability by correctly implementing and exposing ODBC over a single DBMS.  
  
 This section contains the following topics.  
  
-   [Is ODBC the Answer?](../../../odbc/reference/develop-app/is-odbc-the-answer.md)  
  
-   [Choosing a Level of Interoperability](../../../odbc/reference/develop-app/choosing-a-level-of-interoperability.md)  
  
-   [Determining the Target DBMSs and Drivers](../../../odbc/reference/develop-app/determining-the-target-dbmss-and-drivers.md)  
  
-   [Considering Database Features to Use](../../../odbc/reference/develop-app/considering-database-features-to-use.md)  
  
-   [Length of the Product Cycle](../../../odbc/reference/develop-app/length-of-the-product-cycle.md)  
  
-   [Writing an Interoperable Application](../../../odbc/reference/develop-app/writing-an-interoperable-application.md)  
  
-   [Testing Interoperable Applications](../../../odbc/reference/develop-app/testing-interoperable-applications.md)
