---
title: "Installing the Microsoft Connector for SAP BW | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "non-specific"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
caps.latest.revision: 11
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Installing the Microsoft Connector for SAP BW
  The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector for SAP BW for SQL Server 2016 is a component of the SQL Server 2016 Feature Pack. To install the Connector for SAP BW and its documentation, download and run the installer from the [SQL Server 2016 Feature Pack web page](http://go.microsoft.com/fwlink/?LinkId=746297).  
  
> [!IMPORTANT]  
>  The documentation for the Microsoft Connector for SAP BW assumes familiarity with the SAP Netweaver BW environment. For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.  
  
> [!IMPORTANT]  
>  Extracting data from SAP Netweaver BW requires additional SAP licensing. Check with SAP to verify these requirements.  
  
## Required SAP Files  
 To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.  
  
 However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder. (Typically, this folder location is **C:\Windows\system32**.)  
  
## Considerations for 64-bit Computers  
 The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows. On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector for SAP BW has the following additional requirements:  
  
-   To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder. (Typically, this file location is **C:\Windows\system32**.)  
  
-   To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder. (Typically, this folder location is **C:\Windows\SysWow64**.)  
  
  
