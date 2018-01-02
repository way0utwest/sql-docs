---
title: "sys.conversation_groups (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "06/10/2016"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "system-catalog-views"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "conversation_groups_TSQL"
  - "conversation_groups"
  - "sys.conversation_groups"
  - "sys.conversation_groups_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.conversation_groups catalog view"
ms.assetid: 3f35815e-2de4-42a2-a972-8f0141dad0b3
caps.latest.revision: 29
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sys.conversation_groups (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  This catalog view contains a row for each conversation group.  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**conversation_group_id**|**uniqueidentifier**|Identifier for the conversation group. Not NULLABLE.|  
|**service_id**|**int**|Identifier of the service for conversations in this group. Not NULLABLE.|  
|**is_system**|**bit**|Indicates whether this is a system instance or not. NULLABLE.|  
  
## Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] For more information, see [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
  
