---
title: "Create a Visual C# SMO Project in Visual Studio .NET | Microsoft Docs"
ms.custom: ""
ms.date: "08/06/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "smo"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "Visual C# [SMO]"
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
caps.latest.revision: 43
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "On Demand"
---
# How to Create a Visual C# SMO Project in Visual Studio .NET
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  This section describes how to build a simple SMO console application.  
  
 This example imports namespaces, which enables the program to reference SMO types. The import of the **Agent** namespace is optional. Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent. The **Common** namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. The **SqlClient** namespace is used to process SQL exception errors.  
  
### Creating a Visual C# SMO project in Visual Studio.NET  
  
1. Start Visual Studio
  
2. On the **File** menu, click **New** and then **Project**.  The **New Project** dialog box appears.   
  
3. In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Installed** pane, navigate to **Templates**\\**Visual C#**\\**Windows** and select **Console Application**.  
  
4. (Optional) In the **Name** text box, type the name of the new application.  

5. Click **OK** to load the console application template.  

6. Follow the instructions on [Installing SMO](installing-smo.md) to install the package for your project to reference.
  
7. On the **View** menu, click **Code**.
    
8. In the code, before the namespace statement, type the following **using** statements to qualify the types in the SMO namespace:
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
15. SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent. Add these namespaces as they are required.  
  
16. You can now add your SMO code.  
  
  
