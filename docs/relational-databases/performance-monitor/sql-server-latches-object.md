---
title: "SQL Server, Latches Object | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "performance-monitor"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Latches object"
  - "SQLServer:Latches"
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
caps.latest.revision: 23
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQL Server, Latches Object
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches. Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.  
  
 This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.  
  
|SQL Server Latches counters|Description|  
|---------------------------------|-----------------|  
|**Average Latch Wait Time (ms)**|Average latch wait time (in milliseconds) for latch requests that had to wait.|  
|**Average Latch Wait Time Base**|For internal use only.| 
|**Latch Waits/sec**|Number of latch requests that could not be granted immediately.|  
|**Number of SuperLatches**|Number of latches that are currently SuperLatches.|  
|**SuperLatch Demotions/sec**|Number of SuperLatches that have been demoted to regular latches in the last second.|  
|**SuperLatch Promotions/sec**|Number of latches that have been promoted to SuperLatches in the last second.|  
|**Total Latch Wait Time (ms)**|Total latch wait time (in milliseconds) for latch requests in the last second.|  
  
## See Also  
 [Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
