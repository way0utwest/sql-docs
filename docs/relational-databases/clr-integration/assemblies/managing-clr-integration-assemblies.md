---
title: "Managing CLR Integration Assemblies | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "clr"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "database objects [CLR integration], assemblies"
  - "common language runtime [SQL Server], assemblies"
  - "assemblies [CLR integration], managing"
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
caps.latest.revision: 56
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Managing CLR Integration Assemblies
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Managed code is compiled and then deployed in units called an assembly. An assembly is packaged as a DLL or executable (.exe) file. While an executable file can run on its own, a DLL must be hosted in an existing application. Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires you to register the assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used. Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.  
  
 Assembly information is stored in the **sys.assembly_files** table in the database where the assembly has been installed. The **sys.assembly_files** table contains the following columns.  
  
|Column|Description|  
|------------|-----------------|  
|assembly_id|The identifier defined for the assembly. This number is assigned to all objects relating to the same assembly.|  
|name|The name of the object.|  
|file_id|A number identifying each object, with the first object associated with a given **assembly_id** being given the value of 1. If multiple objects are associated with the same **assembly_id**, then each subsequent **file_id** value is incremented by 1.|  
|content|The hexadecimal representation of the assembly or file.|  
  
## In This Section  
 [Creating an Assembly](../../../relational-databases/clr-integration/assemblies/creating-an-assembly.md)  
 Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Altering an Assembly](../../../relational-databases/clr-integration/assemblies/altering-an-assembly.md)  
 Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Dropping an Assembly](../../../relational-databases/clr-integration/assemblies/dropping-an-assembly.md)  
 Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## See Also  
 [CLR Integration Security](../../../relational-databases/clr-integration/security/clr-integration-security.md)   
 [CLR Integration Code Access Security](../../../relational-databases/clr-integration/security/clr-integration-code-access-security.md)  
  
  
