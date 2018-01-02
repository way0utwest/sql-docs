---
title: "Create an APS Domain Administrator (APS)"
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
ms.assetid: ed52bf78-2b0a-4252-98a7-8c2805e22d3d
caps.latest.revision: 7

---
# Create an APS Domain Administrator
Some operations require Analytics Platform System domain administrator privileges. This explains how to create additional appliance domain administrators.  
  
## Create a Domain Administrator  
To have sufficient permissions to configure all APS nodes, the user running the **APS Configuration Manager** (`dwconfig.exe`) must be a member of the **Domain Admins** group. To start and stop the APS services, the user must be a member of the **PdwControlNodeAccess** group.  
  
#### To add a user to the Domain Admins group  
  
1.  Log into the active AD node **(*appliance_domain*-AD01** or ***appliance_domain*-AD02**) using an existing appliance domain administrator account.  
  
2.  On the Start menu, click **Run**. In the **Open** box, type **dsa.msc**. Click **OK**.  
  
3.  In the **Active Directory Users and Computers** program, right-click **Users**, point to **New**, and then click **User**.  
  
4.  In the **New Object – User** dialog box, complete the description of the new user, and then click **Next**.  
  
    Complete the password dialog box, and then click **Next**.  
  
    > [!WARNING]  
    > SQL Server PDW does not support the dollar sign character ($) in the domain administrator or local administrator passwords. A password containing a dollar sign will valid and be usable but can block upgrade and maintenance activities  
  
    Confirm the new user description, and then click **Finish**.  
  
5.  In the list of users, double-click the new user to open the user properties dialog box.  
  
6.  On the **Member Of** tab, click **Add**.  
  
    Type **Domain Admins; PdwControlNodeAccess** and then click **Check Names**. Click **OK**.  
  
    This adds the new user to the **Domain Admins** group and the **PdwControlNodeAccess** group. Click **OK**.  
  
## See Also  
[Launch the Configuration Manager &#40;Analytics Platform System&#41;](launch-the-configuration-manager.md)  
  
