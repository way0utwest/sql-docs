---
title: "ConnectionValidSharedMemory function in dbmslpcn.dll Shared Memory | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "native-client|applications"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6ae35826-7d75-4542-b686-5f79316b6157
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ConnectionValidSharedMemory function in dbmslpcn.dll Shared Memory
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  The function determines whether SQL Server Shared Memory is installed and active.  
  
## Syntax  
  
```cpp  
BOOL ConnectionValidSharedMemory(char * szServerName);  
```  
  
## Parameters  
 *szServerName*  
  
-   Type: **char\***  
  
-   The name of the SQL server.  
  
## Return value  
 Type: **BOOL**  
  
 Returns 0  if not valid; else returns nonzero.  
  
  
