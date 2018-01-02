---
title: "Saving a Package Programmatically | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "building-packages-programmatically"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "SQL Server 2016 Preview"
helpviewer_keywords: 
  - "programmatically saving a package"
  - "saving a package programmatically"
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
caps.latest.revision: 17
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Saving a Package Programmatically
  After building a new package programmatically, or modifying an existing one, you usually want to save your changes.  
  
 All of the methods used in this topic to save packages require a reference to the **Microsoft.SqlServer.ManagedDTS** assembly. After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a **using** or **Imports** statement.  
  
## Saving a Package Programmatically  
 To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:  
  
|Storage Location|Method to Call|  
|----------------------|--------------------|  
|File|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|SSIS Package Store|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> or<br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server. You cannot use "(local)" or "localhost".  
  
## See Also  
 [Save Packages](../../integration-services/save-packages.md)  
  
  
