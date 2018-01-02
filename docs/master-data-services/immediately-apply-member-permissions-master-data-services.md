---
title: "Immediately Apply Member Permissions (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
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
  - "members [Master Data Services], applying permissions immediately"
  - "permissions [Master Data Services], applying member permissions immediately"
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
caps.latest.revision: 6
author: "smartysanthosh"
ms.author: "nagavo"
manager: "craigg"
ms.workload: "Inactive"
---
# Immediately Apply Member Permissions (Master Data Services)
  In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.  
  
## Prerequisites  
 To perform this procedure:  
  
-   You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database. For more information, see [Database Object Security &#40;Master Data Services&#41;](../master-data-services/database-object-security-master-data-services.md).  
  
### To immediately apply hierarchy member permissions  
  
1.  Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.  
  
2.  Create a new query.  
  
3.  Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  Run the query.  
  
## See Also  
 [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [Hierarchy Member Permissions &#40;Master Data Services&#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
