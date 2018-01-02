---
title: "Data Truncation Detection Enabled Using ExtendedAnsiSQL | Microsoft Docs"
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
  - "truncating data [ODBC]"
  - "extendedANSISQL [ODBC], data truncation detection"
ms.assetid: cec2359b-917d-4e1d-9625-5cd678b62f10
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Data Truncation Detection Enabled Using ExtendedAnsiSQL
When the ExtendedAnsiSQL flag is turned on and the application is inserting data into a char or binary column and data is truncated, the truncation will be detected. When the ExtendedAnsiSQL flag is turned off, the data is truncated without warning, as it was in previous versions of the ODBC Desktop Database Drivers.
