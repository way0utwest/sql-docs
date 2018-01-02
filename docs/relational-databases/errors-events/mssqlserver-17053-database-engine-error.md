---
title: "MSSQLSERVER_17053 | Microsoft Docs"
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
  - "17053 (Database Engine error)"
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
caps.latest.revision: 14
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_17053
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|17053|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|OS_ERROR|  
|Message Text|%ls: Operating system error %ls encountered.|  
  
## Explanation  
Generic operating system error occurred.  Not clear what the resulting state is.  
  
## User Action  
Usually this is in conjunction with some other error and should be used to help diagnose that failure. Examples would include reads or writes to data or log files that fail, registry read/write operations, or other unexpected Win32API failures.  
  
