---
title: "Options (SQL Server Always On, Dashboard Page) | Microsoft Docs"
ms.custom: ""
ms.date: "05/17/2016"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "availability-groups"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Alwayson.Dashboard"
ms.assetid: 4369b588-e982-4b57-80a1-beb2e879ce0b
caps.latest.revision: 8
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Options (SQL Server Always On, Dashboard Page)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Use the **SQL Server Always On Dashboard** page of the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the Always On Dashboard.  
  
 **To access this page:**  
  
 On the **Tools** menu, click **Options**, expand the **SQL Server Always On** folder, and then click **Dashboard**.  
  
## On This Page  
 **Turn on automatic refresh.**  
 Click to enable automatic refresh. The options are:  
  
-   The **Refresh interval (in seconds)** field displays the number of seconds at which the dashboard will refresh. The default value is 30. When automatic refresh is enabled, you can edit this field to change the refresh interval.  
  
-   The **Number of connection retries** displays the number of times that the dashboard will attempt to connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for an availability group that the Dashboard is monitoring. The default value is 65535. When automatic refresh is enabled, you can edit this field to change the number of connection retries.  
  
 **Enable your user-defined Always On policy.**  
 If you have defined your own Always On policy, click this option to enable your policy.  
  
## See Also  
 [Use the Always On Dashboard &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
