---
title: "Appliance Time Zone Configuration (Analytics Platform System)"
author: "barbkess" 
ms.author: "barbkess"
manager: "jhubbard"	  
ms.prod: "analytics-platform-system"
ms.prod_service: "mpp-data-warehouse"
ms.service: ""
ms.component:
ms.technology: "mpp-data-warehouse"
ms.custom: ""
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: "sql"
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cea9eeb9-fe05-4e65-b229-539de02ab20a
caps.latest.revision: 18

---
# Appliance Time Zone Configuration
The **Time Zone** page enables you to set the time zone for all nodes on your SQL Server PDW appliance.  
  
## To set the time zone  
  
1.  Launch the Configuration Manager. For more information, see [Launch the Configuration Manager &#40;Analytics Platform System&#41;](launch-the-configuration-manager.md).  
  
2.  Stop the appliance services by using the **Services Status** page in the Configuration Manager. See [PDW Services Status &#40;Analytics Platform System&#41;](pdw-services-status.md) for instructions.  
  
3.  In the left pane of the Configuration Manager, click **Time Zone**. Select the desired time zone from the **Time Zone** drop-down menu. Depending on your location, you may also choose to select the box next to **Automatically adjust clock for Daylight Saving Time**.  
  
4.  Click **Apply** to save your changes.  
  
5.  Restart the appliance services by using the **Services Status** page in the Configuration Manager. If you are also planning to change the privileges, you can do that before restarting the appliance.  
  
![DWConfig Appliance Time](./media/appliance-time-zone-configuration/SQL_Server_PDW_DWConfig_ApplTopTime.png "SQL_Server_PDW_DWConfig_ApplTopTime")  
  
## See Also  
[Launch the Configuration Manager &#40;Analytics Platform System&#41;](launch-the-configuration-manager.md)  
  
