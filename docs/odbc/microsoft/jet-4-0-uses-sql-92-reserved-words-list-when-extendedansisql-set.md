---
title: "Jet 4.0 Uses SQL-92 Reserved Words List when ExtendedAnsiSQL_Set | Microsoft Docs"
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
  - "extendedANSISQL [ODBC], reserved words"
ms.assetid: 7645187e-7777-4c07-9686-0a80d5c5834d
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Jet 4.0 Uses SQL-92 Reserved Words List when ExtendedAnsiSQL_Set
When the ExtendedAnsiSQL flag is turned on, Jet 4.0 uses the SQL-92 reserved words list. Trying to use a SQL-92 reserved word as an unquoted object name will result in a syntax error. When the ExtendedAnsiSQL flag is turned off, the new reserved words can be used as object names as before.
