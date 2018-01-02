---
title: "MSSQLSERVER_5554 | Microsoft Docs"
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
  - "5554 (Database Engine error)"
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_5554
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|MSSQLSERVER|  
|Event ID|5554|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|FS_MINIVER_OVERFLOW|  
|Message Text|The total number of versions for a single file has reached the maximum limit set by the file system.|  
  
## Explanation  
In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.  
  
## User Action  
Try to avoid repeated updates to the data in the same transaction.  
  
