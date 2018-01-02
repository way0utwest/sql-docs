---
title: "Migrate Sybase ASE Databases to SQL Server - Azure SQL DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/30/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssma-sybase"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "sql-ssma"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Azure SQL Database"
  - "SQL Server"
ms.assetid: ed7952d4-8331-44d7-bccf-3440e17238b2
caps.latest.revision: 7
author: "Shamikg"
ms.author: "Shamikg"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Migrating SAP ASE databases to SQL Server - Azure SQL Database (SybaseToSQL)
SQL Server Migration Assistant (SSMA) for SAP Adaptive Server Enterprise (ASE) is a comprehensive environment that helps you quickly migrate SAP ASE databases to [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] or Azure SQL Database. By using SSMA for SAP ASE, you can review database objects and data, assess databases for migration, migrate database objects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] or Azure SQL Database, and then migrate data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] or Azure SQL Database.  
  
## Recommended migration process  
To successfully migrate objects and data from SAP ASE databases to [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] or Azure SQL Database, use the following process:  
  
1.  [Create a new SSMA project](http://msdn.microsoft.com/en-us/11091d95-c488-48c3-891a-743cac94ac93).  
  
    After you create the project, you can set project conversion, migration, and type mapping options. For information about project settings, see [Setting Project Options &#40;SybaseToSQL&#41;](../../ssma/sybase/setting-project-options-sybasetosql.md). For information about customizing data type mappings, see [Mapping Sybase ASE and SQL Server Data Types &#40;SybaseToSQL&#41;](../../ssma/sybase/mapping-sybase-ase-and-sql-server-data-types-sybasetosql.md).  
  
2.  [Connect to the SAP ASE database server](http://msdn.microsoft.com/en-us/a45a2330-9175-4c9e-af38-ef920e350614).  
  
3.  [Connect to an instance SQL Server](http://msdn.microsoft.com/en-us/dd368a1a-45b0-40e9-b4d3-5cdb48c26606) or [Connect to an instance of Azure SQL Database](http://msdn.microsoft.com/en-us/9e77e4b0-40c0-455c-8431-ca5d43849aa7).  
  
4.  [Map SAP ASE database schemas to SQL Server / Azure SQL Database database schemas](http://msdn.microsoft.com/en-us/2c927003-c49d-4fe1-8e3e-5b2899166268).  
  
5.  Optionally, [create assessment reports](http://msdn.microsoft.com/en-us/eb996b7c-1eef-4f73-b5e6-2fa6faf7336c) to assess database objects for conversion and estimate the conversion time.  
  
6.  [Convert SAP ASE database schemas into SQL Server / Azure SQL Database schemas](http://msdn.microsoft.com/en-us/509cb65d-2f54-427a-83d7-37919cc4e3e3).  
  
7.  [Load the converted database objects into SQL Server / Azure SQL Database](http://msdn.microsoft.com/en-us/4c59256f-99a8-4351-9559-a455813dbd06).  
  
    Either save a script and run it in [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] or Azure SQL Database, or synchronize the database objects.  
  
8.  [Migrate data to SQL Server / Azure SQL Database](http://msdn.microsoft.com/en-us/54a39f5e-9250-4387-a3ae-eae47c799811).  
  
9. If necessary, update your database applications.  
  
## See also  
[Installing SSMA for SAP ASE &#40;SybaseToSQL&#41;](../../ssma/sybase/installing-ssma-for-sybase-sybasetosql.md)  
[Getting Started with SSMA for SAP ASE &#40;SybaseToSQL&#41;](../../ssma/sybase/getting-started-with-ssma-for-sybase-sybasetosql.md)  
  
