---
title: "MSSQLSERVER_1105 | Microsoft Docs"
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
  - "1105 (Database Engine error)"
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
caps.latest.revision: 19
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_1105
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|1105|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|NO_MORE_SPACE_IN_FG|  
|Message Text|Could not allocate space for object '%.*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.|  
  
## Explanation  
No disk space is available in a filegroup.  
  
## User Action  
The following actions may make space available in the filegroup:  
  
-   Turn on autogrow.  
  
-   Add more files to the file group.  
  
-   Free disk space by dropping index or tables that are no longer needed.  
  
-   For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.  
  
> [!NOTE]  
> When an index is located on several files, **ALTER INDEX REORGANIZE** can return error 1105 when one of the files is full. The reorganization process is blocked when the process tries to move rows to the full file. To work around this limitation perform an **ALTER INDEX REBUILD** instead of **ALTER INDEX REORGANIZE** or increase the file growth limit of any files that are full.  
  
