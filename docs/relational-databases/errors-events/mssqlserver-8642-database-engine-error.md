---
title: "MSSQLSERVER_8642 | Microsoft Docs"
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
  - "8642 (Database Engine error)"
ms.assetid: fc498059-202f-4d0b-8599-4e784b47c186
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_8642
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|8642|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|EXCHNGSTART_ERR|  
|Message Text|The query processor could not start the necessary thread resources for parallel query execution.|  
  
## Explanation  
Thread resources are low in the server.  
  
## User Action  
Reduce load on the server, and run the query again.  
  
