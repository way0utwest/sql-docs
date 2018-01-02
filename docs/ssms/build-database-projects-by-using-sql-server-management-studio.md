---
title: "Build Database Projects by Using SQL Server Management Studio | Microsoft Docs"
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
  - "scripts [SQL Server], database projects"
  - "database projects [SQL Server]"
  - "projects [SQL Server Management Studio], about projects"
  - "projects [SQL Server Management Studio]"
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Build Database Projects by Using SQL Server Management Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database. [!INCLUDE[msCoName](../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] databases within the context of a script project. [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.  
  
## SQL Server Management Studio  
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)]. This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.  
  
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] includes the following tools:  
  
-   Code Editor is a rich script editor for writing and editing scripts. [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde_md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql_md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.  
  
-   Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)].  
  
-   Template Explorer for locating and scripting templates.  
  
-   Solution Explorer for organizing and storing related scripts as parts of a project.  
  
-   Properties Window for displaying the current properties of selected objects.  
  
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] supports efficient work processes by providing:  
  
-   Disconnected access. You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)].  
  
-   Scripting from any dialog box. You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.  
  
-   Nonmodal dialog boxes. When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] without closing the dialog box.  
  
## Solutions and Script Projects  
Solution Explorer is a utility to store and reopen database solutions. Solutions organize related script projects and files. Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] script files, SQL templates, connection information and other miscellaneous files. When a script is saved in a script project, users are able to:  
  
-   Maintain version control on scripts.  
  
-   Store results options with a script.  
  
-   Organize related scripts in a single script project.  
  
-   Save connection information with scripts.  
  
Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project. If a similar task is required later, you can use group of scripts that were stored in a project. If you have created applications by using [!INCLUDE[msCoName](../includes/msconame_md.md)] [!INCLUDE[vsprvs](../includes/vsprvs_md.md)], you will find Solution Explorer very familiar.  
  
A solution consists of one or more script projects. A project consists of one or more scripts or connections. A project may also include nonscript files.  
  
## See Also  
[Use SQL Server Management Studio](../ssms/use-sql-server-management-studio.md)  
[Writing, Analyzing, and Editing Queries with SQL Server Management Studio](http://msdn.microsoft.com/en-us/062051e4-4b77-4969-98ae-d2547c24ce3e)  
[Solutions &#40;SQL Server Management Studio&#41;](../ssms/solution/solutions-sql-server-management-studio.md)  
  
