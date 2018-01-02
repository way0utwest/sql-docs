---
title: "Hide System Objects in Object Explorer | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-objects"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "hiding system objects"
  - "system objects [SQL Server]"
  - "objects [SQL Server], hiding"
  - "Object Explorer, hiding objects"
ms.assetid: c01d8804-838c-4f75-b78c-80e41e4fffdc
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Hide System Objects in Object Explorer
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
This topic describes how to hide system objects in Object Explorer in [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]. The **Databases** node of Object Explorer contains system objects such as the system databases. Use the **Tools**/**Options** pages to hide the system objects. Some system objects, such as system functions and system data types, are not affected by this setting.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To hide system objects in Object Explorer  
  
1.  On the **Tools** menu, click **Options**.  
  
2.  On the **Environment/Startup** page, select **Hide system objects in Object Explorer**, and then click **OK**.  
  
3.  In the **SQL Server Management Studio** dialog box, click **OK** to acknowledge that SQL Server Management Studio must be restarted for this change to take effect.  
  
4.  Close and reopen SQL Server Management Studio.  
  
