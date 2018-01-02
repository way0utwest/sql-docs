---
title: "sys.service_contract_usages (Transact-SQL) | Microsoft Docs"
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
  - "service_contract_usages"
  - "sys.service_contract_usages"
  - "sys.service_contract_usages_TSQL"
  - "service_contract_usages_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.service_contract_usages catalog view"
ms.assetid: 20af425e-1152-4a46-b1ac-94cff5fc9f02
caps.latest.revision: 29
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sys.service_contract_usages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  This catalog view contains a row per (service, contract) pair.  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**service_id**|**int**|Identifier of the service using the contract. Not NULLABLE.|  
|**service_contract_id**|**int**|Identifier of the contract used by the service. Not NULLABLE.|  
  
## Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] For more information, see [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
  
