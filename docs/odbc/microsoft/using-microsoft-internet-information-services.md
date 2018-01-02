---
title: "Using Microsoft Internet Information Services | Microsoft Docs"
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
  - "ODBC driver for Oracle [ODBC], IIS"
  - "internet information services [ODBC]"
  - "IIS [ODBC]"
ms.assetid: 3328f2f1-b34a-472f-82cf-ad49768ff061
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Using Microsoft Internet Information Services
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Instead, use the ODBC driver provided by Oracle.  
  
 If you have difficulty connecting from within an IIS script (particularly if you receive an ORA-12641 error), add the following line to the Sqlnet.ora file:  
  
```  
SQLNET.AUTHENTICATION_SERVICES = (none)  
```  
  
 This will disable the Secure Network Services so you can connect using anonymous authentication.
