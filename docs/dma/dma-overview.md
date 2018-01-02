---
title: "Overview of Data Migration Assistant (SQL Server) | Microsoft Docs"
ms.custom: ""
ms.date: "10/04/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "dma"
ms.service: ""
ms.component:
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "sql-dma"
ms.tgt_pltfrm: ""
ms.topic: "article"
keywords: ""
helpviewer_keywords: 
  - "Data Migration Assistant, overview"
ms.assetid: ""
caps.latest.revision: ""
author: "HJToland3"
ms.author: "jtoland"
manager: "craigg"
ms.workload: "Inactive"
---

# Overview of Data Migration Assistant

Data Migration Assistant (DMA) enables you to upgrade to a modern data platform by detecting compatibility issues that can impact database functionality in your new version of SQL Server and Azure SQL Database. DMA recommends performance and reliability improvements for your target environment and allows you to move your schema, data, and uncontained objects from your source server to your target server.

## Capabilities

- Assess on-premises SQL Server instance(s) migrating to Azure SQL database(s). The assessment workflow helps you to detect the following issues that can affect Azure SQL database migration and provides detailed guidance on how to resolve them.

  - Migration blocking issues:  Discovers the compatibility issues that block migrating on-premises SQL Server database(s)s to Azure SQL Database(s). DMA provides recommendations to help you address those issues.

  - Partially supported or unsupported features:  Detects partially supported or unsupported features that are currently in use on the source SQL Server instance. DMA provides a comprehensive set of recommendations, alternative approaches available in Azure, and mitigating steps so that you can incorporate into your migration projects.

- Discover issues that can affect an upgrade to an on-premises SQL Server.  These are described as compatibility issues and are organized in the following categories:

  - Breaking changes

  - Behavior changes

  - Deprecated features

- Discover new features in the target SQL Server platform that the database can benefit from after an upgrade. These are described as feature recommendations and are organized in the following categories:

  - Performance

  - Security

  - Storage

- Migrate an on-premises SQL Server instance to a modern SQL Server instance, hosted on premises or on an Azure virtual machine (VM) that is accessible from your on-premises network. The Azure VM can be accessed using VPN or other technologies. The migration workflow helps you to migrate the following components:

  - Schema of databases

  - Data and users

  - Server roles

  - SQL Server and Windows logins

- After the successful migration, applications can connect to the target SQL server databases seamlessly.

## Supported source and target versions

DMA replaces all previous versions of SQL Server Upgrade Advisor and should be used for upgrades for most SQL Server versions. Supported source and target versions follow.

**Sources**
- SQL Server 2005
- SQL Server 2008
- SQL Server 2008 R2
- SQL Server 2012 
- SQL Server 2014
- SQL Server 2016

**Targets**
- SQL Server 2012
- SQL Server 2014
- SQL Server 2016
- Azure SQL Database

## Installation

To install DMA, download the latest version of the tool from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53595), and then run the **DataMigrationAssistant.msi** file.

## See also

[Assess your SQL Server Migration](../dma/dma-assesssqlonprem.md)

[Data Migration Assistant: Configuration settings](../dma/dma-configurationsettings.md)

[Migrate On-Premises SQL Server using Data Migration Assistant](../dma/dma-migrateonpremsql.md)

[Data Migration Assistant: Best Practices](../dma/dma-bestpractices.md)



