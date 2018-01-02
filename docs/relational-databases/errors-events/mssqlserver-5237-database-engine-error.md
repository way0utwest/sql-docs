---
title: "MSSQLSERVER_5237 | Microsoft Docs"
ms.custom: ""
ms.date: "04/04/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "errors-events"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
helpviewer_keywords: 
  - "5237 (Database Engine error)"
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_5237
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|5237|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE|  
|Message Text|DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.|  
  
## Explanation  
An internal error resulted in DBCC not being able to execute the query to check indexed views.  
  
## User Action  
Rerun the DBCC command.  
  
