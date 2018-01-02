---
title: "Introduction to SQL Server Management Studio for BI | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SQL Server Management Studio for Integration Services"
  - "SQL Server Management Studio for Reporting Services"
  - "SQL Server Management Studio for Analysis Services"
ms.assetid: ffaa77b7-03d0-4d7a-aa42-c5091a4f2ceb
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Introduction to SQL Server Management Studio for Business Intelligence
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
To access, configure, manage, and administer [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion_md.md)], and [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion_md.md)], use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)]. Although all three business intelligence technologies rely on [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)], the administrative tasks associated with each of these technologies are slightly different.  
  
> [!NOTE]  
> To create and modify [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion_md.md)], and [!INCLUDE[ssISnoversion](../includes/ssisnoversion_md.md)] solutions, use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull_md.md)], not [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)]. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull_md.md)] is a development environment that is based on [!INCLUDE[msCoName](../includes/msconame_md.md)][!INCLUDE[vsprvs](../includes/vsprvs_md.md)].  
  
## Managing Analysis Services Solutions Using SQL Server Management Studio  
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] enables you to manage [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] objects, such as performing back-ups and processing objects.  
  
[!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] provides an [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] Script project in which you develop and save scripts written in Multidimensional Expressions (MDX), Data Mining Extensions (DMX), and XML for Analysis (XMLA). You use [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] Scripts projects to perform management tasks or re-create objects, such as database and cubes, on [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] instances. For example, you can develop an XMLA script in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] Script project that creates new objects directly on an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] instance. The [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)] Scripts projects can be saved as part of a solution and integrated with source code control.  
  
For more information about how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)], see [Developing and Implementing Using SQL Server Management Studio](http://msdn.microsoft.com/en-us/c4f5a06b-e2e4-4660-a3a8-6fd356742c02).  
  
## Managing Integration Services Solutions Using SQL Server Management Studio  
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] enables you to use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion_md.md)] service to manage packages and monitor running packages. You can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] to organize packages into folders, run packages, import and export packages, migrate Data Transformation Services (DTS) packages, and upgrade [!INCLUDE[ssISnoversion](../includes/ssisnoversion_md.md)] packages.  
  
## Managing Reporting Services Projects Using SQL Server Management Studio  
Use SQL Server Management Studio to enable Reporting Services features, administer the server and databases, and manage roles and jobs.  
  
You manage shared schedules by using the Shared Schedules folder, and manage report server databases (ReportServer, ReportServerTempdb). You also create a RSExecRole in the Master system database when you move a report server database to a new or different SQL Server Database Engine ([!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] [!INCLUDE[ssDE](../includes/ssde_md.md)]). For more information about these tasks, see the following topics:  
  
-   [Management Studio How-to Topics](http://msdn.microsoft.com/en-us/60685458-9108-47bf-820a-5e7db454d408)  
  
-   [Administering a Report Server Database](http://msdn.microsoft.com/en-us/97b2e1b5-3869-4766-97b9-9bf206b52262)  
  
-   [How to: Create the RSExecRole](http://msdn.microsoft.com/en-us/7ac17341-df7e-4401-870e-652caa2859c0)  
  
You also manage the server by enabling and configuring various features, setting server defaults, and managing roles and jobs. For more information about these tasks, see the following topics:  
  
-   [How to: Set Report Server Properties (Management Studio)](http://msdn.microsoft.com/en-us/1ed0f84b-b12a-4e49-b65c-a11a99f9093f)  
  
-   [How to: Create, Delete, or Modify a Role (Management Studio)](http://msdn.microsoft.com/en-us/3d1d56e6-a283-44a7-8417-36cb4d2c74d1)  
  
-   [Enabling and Disabling Client-Side Printing for Reporting Services](http://msdn.microsoft.com/en-us/0e709c96-7517-4547-8ef6-5632f8118524)  
  
## See Also  
[Developing and Implementing Using SQL Server Data Tools](http://msdn.microsoft.com/en-us/132ed779-3ec8-4734-9698-802116d1b017)  
[Reporting Services in SQL Server Data Tools](http://msdn.microsoft.com/en-us/0903c7b2-ac59-45f1-b7d0-922ecd9d76f8)  
  
