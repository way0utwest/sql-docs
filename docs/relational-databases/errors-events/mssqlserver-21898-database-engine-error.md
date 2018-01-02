---
title: "MSSQLSERVER_21898 | Microsoft Docs"
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
  - "21898 (Database Engine error)"
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_21898
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|21898|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|SQLErrorNum21898|  
|Message Text|The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'. Run **sp_changedistpublisher** at distributor '%s' to change the distribution database used by the publisher to '%s'.|  
  
## Explanation  
**sp_validate_redirected_publisher** queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher. This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.  
  
## User Action  
Execute stored procedure **sp_changedistpublisher** to change the distribution database for the new publisher to that used by the original publisher.  
  
> [!NOTE]  
> Running **sp_changedistpublisher** will address the problem if the wrong distribution database was entered when **sp_adddistpublisher** was run at the distributor for the publisher. However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate. Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher’s distribution database in order for the new publisher to function as a suitable host.  
  
