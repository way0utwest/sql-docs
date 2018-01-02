---
title: "Explicitly Allocated Descriptors | Microsoft Docs"
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
  - "descriptors [ODBC], allocating and freeing"
  - "explicitly allocated descriptors [ODBC]"
  - "allocating and freeing descriptors [ODBC]"
ms.assetid: f590251d-56a6-4d58-a405-9e85e68fbc47
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Explicitly Allocated Descriptors
An application can explicitly allocate an application descriptor on a connection at any time it is connected to the database. By specifying that descriptor handle as an attribute of a statement handle using **SQLSetStmtAttr**, the application directs the driver to use that descriptor in place of the corresponding implicitly allocated application descriptors. The application cannot specify alternate implementation descriptors.  
  
 An application can associate an explicitly allocated descriptor with more than one statement. Only when an application is actually connected to the database can a descriptor be an explicitly allocated descriptor. The application can free such a descriptor explicitly, or implicitly by freeing its connection.
