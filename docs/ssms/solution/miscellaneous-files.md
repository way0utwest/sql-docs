---
title: "Miscellaneous Files | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-solutions"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "files [SQL Server Management Studio], miscellaneous"
  - "projects [SQL Server Management Studio], files"
  - "solutions [SQL Server Management Studio], files"
  - "miscellaneous files folder [SQL Server]"
ms.assetid: 3c952b0b-8f5f-4d86-9e5d-616c10b9df0d
caps.latest.revision: 5
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Miscellaneous Files
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Files that that are external to any project are called *miscellaneous files*. When you have a solution open, you can open and modify miscellaneous files related to the project. A file is classified as a miscellaneous file if the file extension is not associated with the project code editor. For example, in a [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Scripts Project, files with the extension .txt or .mdx will be treated as miscellaneous files. In an MDX project, files with the extension of .txt or .sql will be treated as miscellaneous files. To associate a file extension with a code editor, see [How to: Associate File Extensions to a Code Editor](http://msdn.microsoft.com/en-us/193630f4-93de-4950-8f36-68702531f925).  
  
There are a number of reasons why it is useful to be able to add miscellaneous files to your project. You might have a file that is not necessarily a recognized script but integral to the solution's development. Common examples include development notes or instructions, data files, and code clips.  
  
Miscellaneous files provide flexibility. For example, suppose you have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Scripts Project that has several scripts for creation of tables and stored procedures in your database. You also have several data files for the tables with file extensions .BCP and execution instructions in a README.TXT file. You can attach the data and the README files as miscellaneous files to the project to take advantage of source control and other features of the project system.  
  
[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] menus and toolbars change according to the format of the file you open. When you open a text file, for example, the Text Editor toolbar appears. If you open an XML Schema file, the XML Schema toolbar appears. While editing your XML Schema, the Text Editor toolbar is unavailable. When you switch between a project file and a miscellaneous file, all project-related commands and toolbars are replaced by those relevant to the miscellaneous file.  
  
## See Also  
[Files That Manage Solutions and Projects](../../ssms/solution/files-that-manage-solutions-and-projects.md)  
[Solutions &#40;SQL Server Management Studio&#41;](../../ssms/solution/solutions-sql-server-management-studio.md)  
[Projects &#40;SQL Server Management Studio&#41;](../../ssms/solution/projects-sql-server-management-studio.md)  
  
