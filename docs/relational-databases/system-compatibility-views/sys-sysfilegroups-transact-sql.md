---
title: "sys.sysfilegroups (Transact-SQL) | Microsoft Docs"
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
  - "sysfilegroups_TSQL"
  - "sys.sysfilegroups"
  - "sysfilegroups"
  - "sys.sysfilegroups_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sysfilegroups system table"
  - "sys.sysfilegroups compatibility view"
ms.assetid: e567fa07-31cd-43cc-b8c7-ba6108baca80
caps.latest.revision: 30
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sys.sysfilegroups (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contains one row for each file group in a database. There is at least one entry in this table that is for the primary file group.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**groupid**|**smallint**|Group identification number unique for each database.|  
|**allocpolicy**|**smallint**|Reserved|  
|**status**|**int**|0x8 = Read-only<br /><br /> 0x10 = Default|  
|**groupname**|**sysname**|Name of the file group.|  
  
## See Also  
 [Mapping System Tables to System Views &#40;Transact-SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Compatibility Views &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
