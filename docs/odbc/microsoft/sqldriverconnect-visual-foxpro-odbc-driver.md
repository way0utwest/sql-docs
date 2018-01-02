---
title: "SQLDriverConnect (Visual FoxPro ODBC Driver) | Microsoft Docs"
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
  - "SQLDriverConnect function [ODBC], Visual FoxPro ODBC Driver"
ms.assetid: 10492c8f-3a18-4971-9db8-879e878083b9
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLDriverConnect (Visual FoxPro ODBC Driver)
> [!NOTE]  
>  This topic contains Visual FoxPro ODBC Driver-specific information. For general information about this function, see the appropriate topic under [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Support: Full  
  
 ODBC API Conformance: Level 1  
  
 Connects to an existing data source, which can be either a [database](../../odbc/microsoft/visual-foxpro-terminology.md) or a directory of [free tables](../../odbc/microsoft/visual-foxpro-terminology.md). The ODBC attribute keywords UID and PWD are ignored. The following table lists the additional supported attribute keywords.  
  
|ODBC attribute keyword|Attribute value|  
|----------------------------|---------------------|  
|DSN||  
|UID|Ignored by the Visual FoxPro ODBC Driver but does not generate an error.|  
|PWD|Ignored by the Visual FoxPro ODBC Driver but does not generate an error.|  
|Driver|The name and location of the Visual FoxPro ODBC Driver; implemented by the Driver Manager.|  
  
|Visual FoxPro ODBC Driver attribute keyword|Attribute value|  
|-------------------------------------------------|---------------------|  
|BackgroundFetch|"Yes" or "No"|  
|Collate|"Machine" or other collating sequence. For a list of supported collating sequences, see [SET COLLATE](../../odbc/microsoft/set-collate-command.md).|  
|Description||  
|Exclusive|"Yes" or "No"|  
|SourceDB|A fully qualified path to a directory containing zero or more [free tables](../../odbc/microsoft/visual-foxpro-terminology.md), or the absolute path and file name for a [database](../../odbc/microsoft/visual-foxpro-terminology.md).|  
|SourceType|"DBC" or "DBF"|  
|Version||  
  
 If the data source name is not specified, the Driver Manager prompts the user for the information (depending on the setting of the *fDriverCompletion* argument) and then continues. If more information is required, the Visual FoxPro ODBC Driver displays the prompt dialog.  
  
 For more information, see [SQLDriverConnect](../../odbc/reference/syntax/sqldriverconnect-function.md) in the *ODBC Programmer's Reference*.
