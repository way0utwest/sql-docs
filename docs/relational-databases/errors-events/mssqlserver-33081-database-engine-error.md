---
title: "MSSQLSERVER_33081 | Microsoft Docs"
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
  - "33081 (Database Engine error)"
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Inactive"
---
# MSSQLSERVER_33081
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## Details  
  
|||  
|-|-|  
|Product Name|SQL Server|  
|Event ID|33081|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|SEC_DLL_TRUST_VERIFICATION_FAILED|  
|Message Text|Failed to load cryptographic provider '%.*ls' due to an invalid Authenticode signature or invalid file path.  Check previous messages for other failures.|  
  
## Explanation  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to load the cryptographic provider listed in the error message. There are several Win API failures which might cause this error. The ring buffer contains the name of the failed API and the Windows error code returned by the API. To get more information, query the sys.dm_os_ring_buffers view using the following query.  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## User Action  
To investigate the problem, search for the Windows error code in MSDN (http://msdn.microsoft.com/). Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information. If you need to contact CSS, collect the following information for our support staff.  
  
-   The error log showing the failed to load cryptographic provider error.  
  
-   The output from the following statement:  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
> Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.  
  
