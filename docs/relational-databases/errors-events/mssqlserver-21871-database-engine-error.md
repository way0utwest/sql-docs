---
title: "MSSQLSERVER_21871 | Microsoft Docs"
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
  - "21871 (Database Engine error)"
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_21871
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|21871|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|SQLErrorNum21871|  
|Message Text|Publisher %s of database %s has not been redirected.|  
  
## Explanation  
**sp_validate_replica_hosts_as_publishers** checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.  **sp_validate_replica_hosts_as_publishers** returns error 21871 when no entry is found.  
  
## User Action  
**sp_validate_replica_hosts_as_publishers** is only relevant for redirected publishers. If the publisher database is a member of an availability group, use the stored procedure **sp_redirect_publisher** to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.  
  
