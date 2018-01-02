---
title: "Using Microsoft Component Services | Microsoft Docs"
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
  - "ODBC driver for Oracle [ODBC], component services"
  - "component services [ODBC]"
ms.assetid: 06450562-d8f3-4987-b7bd-4a70223ff937
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Using Microsoft Component Services
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Instead, use the ODBC driver provided by Oracle.  
  
 You can enable an Oracle database to work with transactional Component Services (or MTS, if you are using Windows NT) on Microsoft Windows NT/Windows 2000 and Microsoft Windows 95/98. To enable an Oracle database to work with Component Services that support transactions, system administrators should create a view named V$XATRANS$. To create this script, you must run an Oracle-supplied script. For more information, see the Component Services Help or your Oracle documentation.
