---
title: "MSSQLSERVER_9692 | Microsoft Docs"
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
  - "9692 (Database Engine error)"
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_9692
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|9692|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|SB2_CANT_LISTEN_PORT_IN_USE|  
|Message Text|The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.|  
  
## Explanation  
Another program on the computer is using the TCP port indicated.  
  
## User Action  
Run **netstat -aon** to determine what program is using the port. Disable that application or specify a different port for Service Broker.  
  
