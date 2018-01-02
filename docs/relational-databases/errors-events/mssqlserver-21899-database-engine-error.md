---
title: "MSSQLSERVER_21899 | Microsoft Docs"
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
  - "21899 (Database Engine error)"
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_21899
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|21899|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|SQLErrorNum21899|  
|Message Text|The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.|  
  
## Explanation  
**sp_validate_redirected_publisher** queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers. Error 21899 is returned if this query fails. The validation query requires access to the published database at the redirected publisher. If the login specified when **sp_adddistpublisher** is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.  
  
## User Action  
Review the cited error message to determine the cause of the failure and take appropriate corrective action  
  
