---
title: "sysdbmaintplan_jobs (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "06/10/2016"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "system-tables"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sysdbmaintplan_jobs"
  - "sysdbmaintplan_jobs_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sysdbmaintplan_jobs system table"
ms.assetid: bc65cd70-6ef2-4c17-be11-877ecf4efe50
caps.latest.revision: 28
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sysdbmaintplan_jobs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  This table is included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to preserve existing information for instances upgraded from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not change the contents of this table. This table is stored in the **msdb** database.  
  
 [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  

  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**plan_id**|**uniqueidentifier**|Database maintenance plan ID.|  
|**job_id**|**uniqueidentifier**|ID of a job associated with the database maintenance plan.|  
  
  
