---
title: "Administer Servers with SQL Server Management Studio | Microsoft Docs"
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
  - "SQL Server Management Studio [SQL Server], servers"
  - "servers [SQL Server], administering"
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
caps.latest.revision: 7
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Administer Servers with SQL Server Management Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[msCoName](../includes/msconame_md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] and Azure SQL Database administrator's server management requirements. In [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] family and graphically browse its contents. A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde_md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion_md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion_md.md)] or Azure SQL Database.  
  
The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window. To display a tool, on the **View** menu, click the tool name. To display the Query Editor tool, click the **New Query** button on the toolbar.  
  
> [!IMPORTANT]  
> Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] is unencrypted by default. Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] unless you have established an encrypted connection. For more information, see [How to: Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)](http://msdn.microsoft.com/en-us/e1e55519-97ec-4404-81ef-881da3b42006).  
  
Use [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] to:  
  
-   Register servers.  
  
-   Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde_md.md)], [!INCLUDE[ssAS](../includes/ssas_md.md)], [!INCLUDE[ssRS](../includes/ssrs_md.md)],  [!INCLUDE[ssIS](../includes/ssis_md.md)] or Azure SQL Database.  
  
-   Configure server properties.  
  
-   Manage database and [!INCLUDE[ssAS](../includes/ssas_md.md)] objects such as cubes, dimensions, and assemblies.  
  
-   Create objects, such as databases, tables, cubes, database users, and logins.  
  
-   Manage files and filegroups.  
  
-   Attach or detach databases.  
  
-   Launch scripting tools.  
  
-   Manage security.  
  
-   View system logs.  
  
-   Monitor current activity.  
  
-   Configure replication.  
  
-   Manage full-text indexes.  
  
To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] Configuration Manager.  
  
## See Also  
[Use SQL Server Management Studio](../ssms/use-sql-server-management-studio.md)  
[How to: View server properties (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/55f3ac04-5626-4ad2-96bd-a1f1b079659d)  
  
