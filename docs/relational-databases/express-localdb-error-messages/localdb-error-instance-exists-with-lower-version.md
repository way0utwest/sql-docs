---
title: "LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Microsoft Docs"
ms.custom: ""
ms.date: "03/06/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "localdb"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
caps.latest.revision: 8
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|258|  
|Event Source|SQL Server Local Database Runtime 12.0|  
|Component|Local Database Runtime API|  
|Message Text|Unable to create the Local Database instance with specified version. An instance with the same name already exists, but it has lower version than the specified version.|  
  
## Explanation  
 The specified instance already exists but its version is lower than requested.  
  
## User Action  
 Delete the existing instance and retry the operation.  
  
  
