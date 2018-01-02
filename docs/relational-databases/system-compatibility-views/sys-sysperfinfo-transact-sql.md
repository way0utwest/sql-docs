---
title: "sys.sysperfinfo (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/15/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "system-compatibility-views"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sysperfinfo_TSQL"
  - "sys.sysperfinfo_TSQL"
  - "sys.sysperfinfo"
  - "sysperfinfo"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.sysperfinfo compatibility view"
  - "sysperfinfo system table"
ms.assetid: e22a81cd-27de-4690-9443-6aad6393bd3c
caps.latest.revision: 40
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sys.sysperfinfo (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contains a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] representation of the internal performance counters that can be displayed through the Windows System Monitor.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**object_name**|**nchar(128)**|Performance object name, such as **SQLServer:LockManager** or **SQLServer:BufferManager**.|  
|**counter_name**|**nchar(128)**|Name of the performance counter within the object, such as **Page Requests** or **Locks Requested**.|  
|**instance_name**|**nchar(128)**|Named instance of the counter. For example, there are counters maintained for each type of lock, such as **Table**, **Page**, **Key**, and so on. The instance name distinguishes between similar counters.|  
|**cntr_value**|**bigint**|Actual counter value. Frequently, this will be a level or monotonically increasing counter that counts occurrences of the instance event.|  
|**cntr_type**|**int**|Type of counter as defined by the Windows performance architecture.|  
  
## See Also  
 [Mapping System Tables to System Views &#40;Transact-SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Compatibility Views &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
