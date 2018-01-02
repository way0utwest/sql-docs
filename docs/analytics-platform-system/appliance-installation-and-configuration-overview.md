---
title: "Appliance Installation and Configuration Overview (Analytics Platform System)"
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
ms.assetid: 10934f62-4acf-4ca5-b550-f426ba81fe11
caps.latest.revision: 23

---
# Appliance Installation and Configuration Overview
Walks SQL Server PDW appliance administrators through the initial steps to set up and get started using your new SQL Server PDW appliance.  
  
<!-- MISSING LINKS ## <a name="BeforeYouBegin"></a>Before You Begin  
Before you begin to install, configure, and use your new appliance, we recommend reviewing information about the appliance components. Review the following to familiarize yourself with the appliance:  
  
-   Review [Understanding the Appliance Nodes and Hardware (SQL Server PDW)](assetId:///f60f419f-d1e1-403d-8cf9-07e7ef6d6627) to be sure you understand the components included in your new appliance.  
  
-   Review [Connecting to SQL Server PDW (SQL Server PDW)](assetId:///721851d5-e521-4d5b-ba6d-8e2e9d3c7808) to understand how and when appliance administrators will connect to each appliance node.  
-->

## <a name="InstallHardware"></a>1. Install the Hardware  
Your new appliance will be delivered on pallets to the dock at your data center.  
  
> [!IMPORTANT]  
> In some cases, your IHV will unpack, rack, and connect the appliance for you in your data center. If so, these instructions are not necessary and you can skip to the [3. Configure the Appliance](#ConfigureAppliance) section below.  
  
If your IHV is not performing the hardware install, use the following steps to install the hardware.  
  
|||  
|-|-|  
|**Task**|**Description**|  
|Confirm documentation|Confirm that you have received all necessary documents and information from your independent hardware vendor (IHV). See [Information to Obtain from Your IHV &#40;Analytics Platform System&#41;](information-to-obtain-from-your-ihv.md).|  
|Install hardware|Verify the data center can accommodate the appliance. Move the appliance components to the data center. Rack the network switches, PDUs, and cabling. See [Hardware Installation &#40;Analytics Platform System&#41;](hardware-installation.md).|  
  
## <a name="PowerOnAppliance"></a>2. Power On the Appliance  
  
|||  
|-|-|  
|**Task**|**Description**|  
|Power on the appliance|Power on each appliance component node in the required order, waiting as necessary to confirm that no errors are encountered.|  
  
## <a name="ConfigureAppliance"></a>3. Configure the Appliance  
  
|||  
|-|-|  
|**Task**|**Description**|  
|||  
|Configure the appliance by using the SQL Server PDW**Configuration Manager**|Use the Configuration Manager to set appliance passwords, time zones, network and firewall settings, security certificates, and performance and other settings on your appliance. See [Appliance Configuration &#40;Analytics Platform System&#41;](appliance-configuration.md).|  
  
> [!WARNING]  
> Configuration changes should only be made using the SQL Server PDW**Configuration Manager**. Changes not exposed through **Configuration Manager** are not supported. For example, the SQL Server PDW appliance only supports the US-English language setting.  
  
## <a name="SoftwareServicing"></a>4. Set Up Software Servicing  
  
|||  
|-|-|  
|**Task**|**Description**|  
|Apply SQL Server PDW updates|(Optional) You may need to apply one or more SQL Server PDW updates to update your SQL Server PDW software to the latest version. See [Apply Analytics Platform System Hotfixes &#40;Analytics Platform System&#41;](apply-analytics-platform-system-hotfixes.md).|  
|Configure Windows Server Update Services|Configure the appliance to receive updates from Windows Server Update Services for supporting software. See [Download and Apply Microsoft Updates &#40;Analytics Platform System&#41;](download-and-apply-microsoft-updates.md).|  
  
## <a name="NextSteps"></a>Next Steps  
After you have completed all of the preceding steps, your appliance is ready for use. You or other personnel at your location can proceed with the following tasks.  
  
|||  
|-|-|  
|**Task**|**Description**|  
|Install SQL Server PDW drivers and configure connectivity|Configure local computers to connect to SQL Server PDW by using SQL Server Data Tools, sqlcmd, business intelligence software, or other tools. <!-- MISSING LINKS See [Client Tools (SQL Server PDW)](assetId:///721851d5-e521-4d5b-ba6d-8e2e9d3c7808).-->|  
|Create logons and server roles, and assign permissions|Plan and create logons and server roles that will allow users to log on to SQL Server PDW with the appropriate permissions. <!-- MISSING LINKS See [PDW Permissions &#40;SQL Server PDW&#41;](../sqlpdw/pdw-permissions-sql-server-pdw.md).-->|  
|Configure the Azure Data Management Gateway|The Gateway enables Azure users to access on-premises APS data by exposing APS data as secure OData feeds. The Gateway is installed on the Control node already. Ask Microsoft for assistance with configuration.|  
|Monitor queries and appliance users|Use the Admin Console and other resources to monitor the queries and appliance users. See [Monitor the Appliance by Using the Admin Console &#40;Analytics Platform System&#41;](monitor-the-appliance-by-using-the-admin-console.md)<!-- MISSING LINKS and [User Sessions &#40;SQL Server PDW&#41;](../sqlpdw/user-sessions-sql-server-pdw.md)-->.|  
|Load data to SQL Server PDW|Load data to your appliance. <!-- MISSING LINKS See [Load &#40;SQL Server PDW&#41;](../sqlpdw/load-sql-server-pdw.md).-->|  
|Create a disaster recovery plan|Plan how you will protect your data from hardware failures or data overwrites. Create a plan using regular backups and restore plans in case of data corruption or loss. <!-- MISSING LINKS See [Create a Disaster Recovery Plan &#40;SQL Server PDW&#41;](../sqlpdw/create-a-disaster-recovery-plan-sql-server-pdw.md).-->|  
|Monitor the appliance|Monitor the appliance state, health, and performance by using system views, logs, and the Admin Console. Correct or report any problems. See [Monitor Appliance Health State &#40;Analytics Platform System&#41;](../relational-databases/system-dynamic-management-views/sys-dm-pdw-component-health-status-transact-sql.md).|  
