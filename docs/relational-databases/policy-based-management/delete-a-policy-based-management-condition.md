---
title: "Delete a Policy-Based Management Condition | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
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
  - "Policy-Based Management, delete policy conditions"
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Delete a Policy-Based Management Condition
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
 **In This Topic**  
  
-   **Before you begin:**  
  
     [Security](#Security)  
  
-   **To delete a condition, using:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Before You Begin  
  
###  <a name="Security"></a> Security  
  
####  <a name="Permissions"></a> Permissions  
 Requires membership in the PolicyAdministratorRole role in the msdb database.  
  
##  <a name="SSMSProcedure"></a> Using SQL Server Management Studio  
  
#### To delete a condition  
  
1.  In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.  
  
2.  Click the plus sign to expand the **Management** folder.  
  
3.  Click the plus sign to expand **Policy Management**.  
  
4.  Click the plus sign to expand the **Conditions** folder.  
  
5.  Right-click the condition that you want to delete and select **Delete**.  
  
6.  In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.  
  
  
