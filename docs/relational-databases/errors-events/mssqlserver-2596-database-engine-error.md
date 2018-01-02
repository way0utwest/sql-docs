---
title: "MSSQLSERVER_2596 | Microsoft Docs"
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
  - "2596 (Database Engine error)"
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
caps.latest.revision: 18
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_2596
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|2596|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|DBCC_DATABASE_IN_READ_ONLY_MODE|  
|Message Text|The repair statement was not processed. The database cannot be in read-only mode.|  
  
## Explanation  
This message indicates that the database is in read-only mode. Repairs are not possible when a database is in read-only mode.  
  
## User Action  
Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.  
  
## See Also  
[ALTER DATABASE &#40;Transact-SQL&#41;](~/t-sql/statements/alter-database-transact-sql-set-options.md)  
  
