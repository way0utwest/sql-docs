---
title: "Setting ExtendedAnsiSQL | Microsoft Docs"
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
  - "extendedANSISQL [ODBC], setting"
ms.assetid: 37b775d1-65ac-45ac-8572-454bc4e3c1a2
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Setting ExtendedAnsiSQL
The attribute can be controlled in the connection string by adding the ExtendedAnsiSQL attribute:  
  
|Value|Description|  
|-----------|-----------------|  
|ExtendedAnsiSQL=0 (default)|This setting does not enable the new features.|  
|ExtendedAnsiSQL=1|This setting enables the new features.|  
  
 The attribute can also be set in a DSN through the **Advanced Options** dialog box when configuring a DSN through Control Panel.  
  
 Setting the attribute to 0 disables the new features; setting it to 1 enables the new features.  
  
 The attribute can also be set using SQLSetConnectAttr(). The attribute value is 65501 and is set to a SQLINTEGER value of 1 or 0, as documented in the preceding table. It can be called before or after connecting, but it is better to call it after connecting because of the order in which the driver processes cached connection attributes and connection strings.
