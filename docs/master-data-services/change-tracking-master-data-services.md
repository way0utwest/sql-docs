---
title: "Change Tracking (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/15/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "mds"
ms.service: ""
ms.component: "non-specific"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "change tracking [SQL Server]"
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
caps.latest.revision: 7
author: "smartysanthosh"
ms.author: "nagavo"
manager: "craigg"
ms.workload: "Inactive"
---
# Change Tracking (Master Data Services)
  In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes. Use change tracking when you don’t know what the new value will be, but instead want to know if any change occurred.  
  
## Configuring Change Tracking  
 To configure change tracking, you add an attribute to a change tracking group. The group can contain one or many attributes. Then, you create a business rule to define the action that is taken when any of the attributes in the group change.  
  
> [!NOTE]  
>  Change tracking business rules consider staged (imported) data to be changed.  
  
## Related Tasks  
  
|Task Description|Topic|  
|----------------------|-----------|  
|Add attributes to a change tracking group.|[Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|Create a business rule that initiates actions based on attribute changes.|[Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;](../master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## Related Content  
  
-   [Validation &#40;Master Data Services&#41;](../master-data-services/validation-master-data-services.md)  
  
-   [Business Rules &#40;Master Data Services&#41;](../master-data-services/business-rules-master-data-services.md)  
  
-   [Attributes &#40;Master Data Services&#41;](../master-data-services/attributes-master-data-services.md)  
  
  
