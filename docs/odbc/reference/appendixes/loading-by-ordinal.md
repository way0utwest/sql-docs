---
title: "Loading by Ordinal | Microsoft Docs"
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
  - "backward compatibility [ODBC], loading by ordinal"
  - "compatibility [ODBC], loading by ordinal"
  - "loading by ordinal [ODBC]"
ms.assetid: 337d90ab-68eb-4940-a2f3-f7d5693ee766
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Loading by Ordinal
In ODBC 2.*x*, loading by ordinal could be performed to improve the performance of the connection process. An ODBC 2.*x* driver exports a dummy function with the ordinal 199; when the Driver Manager detects it, it resolves the addresses of the ODBC functions by ordinal, not by name. This functionality is still supported for ODBC 2.*x* drivers but is not supported for ODBC 3*.x* drivers.
