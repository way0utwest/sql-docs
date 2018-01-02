---
title: "MSSQLSERVER_3452 | Microsoft Docs"
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
  - "3452 (Database Engine error)"
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_3452
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|3452|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|REC_CHECKIDENTITY|  
|Message Text|Recovery of database '%.*ls' (%d) detected possible identity value inconsistency in table ID %d. Run DBCC CHECKIDENT ('%.\*ls').|  
  
## Explanation  
During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.  
  
## User Action  
Run DBCC CHECKIDENT.  
  
