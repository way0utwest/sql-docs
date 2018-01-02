---
title: "Validate SSIS packages deployed to Azure | Microsoft Docs"
ms.date: "11/27/2017"
ms.topic: "article"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "lift-shift"
ms.suite: "sql"
ms.custom: ""
ms.technology: 
  - "integration-services"
author: "douglaslMS"
ms.author: "douglasl"
manager: "craigg"
---
# Validate SSIS packages deployed to Azure
When you deploy a SQL Server Integration Services (SSIS) project to the SSIS Catalog database (SSISDB) on an Azure server, the Package Deployment Wizard adds an additional validation step after the **Review** page. This validation step checks the packages in the project for known issues that may prevent the packages from running as expected in the Azure SSIS Integration Runtime. Then the wizard displays any applicable warnings on the **Validate** page.

> [!IMPORTANT]
> The validation described in this article occurs when you deploy a project with SQL Server Data Tools (SSDT) version 17.4 or later. To get the latest version of SSDT, see [Download SQL Server Data Tools (SSDT)](../../ssdt/download-sql-server-data-tools-ssdt.md).

For more info about the Package Deployment Wizard, see [Deploy Integration Services (SSIS) Projects and Packages](../packages/deploy-integration-services-ssis-projects-and-packages.md).

## Validate connection managers

The wizard checks certain connection managers for the following issues, which may cause the connection to fail:
- **Windows authentication**. If a connection string uses Windows authentication, validation raises a warning. Windows authentication requires additional configuration steps. For more info, see [Connect to on-premises data sources with Windows Authentication](ssis-azure-connect-with-windows-auth.md).
- **File path**. If a connection string contains a hard-coded local file path like `C:\\...`, validation raises a warning. Packages that contain an absolute path may fail.
- **UNC path**. If a connection string contains a UNC pathif a connection string contains a UNC path, validation raises a warning. Packages that contain a UNC path may fail, typically because a UNC path requires Windows authentication to access.
- **Host name**. If a server property contains host name instead of IP address, validation raises a warning. Packages that contain host name may fail, typically because the Azure virtual network requires the correct DNS configuration to support DNS name resolution.
- **Provider or driver**. If a provider or driver is not supported, validation raises a warning. Only a small number of built-in providers and drivers are supported at this time.

The wizard does the following validation checks for the connection managers in the list.

| Connection Manager | Windows authentication | File path | UNC path | Host name | Provider or driver |
|--------------------|----------|-----------|-----|-----------|-------------------|
| Ado                | ✓        |           |     | ✓         | ✓                 |
| AdoNet             | ✓        |           |     | ✓         | ✓                 |
| Cache              |          | ✓         | ✓   |           |                   |
| Excel              |          | ✓         | ✓   |           |                   |
| File               |          | ✓         | ✓   |           |                   |
| FlatFile           |          | ✓         | ✓   |           |                   |
| Ftp                |          |           |     | ✓         |                   |
| MsOLAP100          |          |           |     | ✓         | ✓                 |
| MultiFile          |          | ✓         | ✓   |           |                   |
| MultiFlatFile      |          | ✓         | ✓   |           |                   |
| OData              | ✓        |           |     | ✓         |                   |
| Odbc               | ✓        |           |     | ✓         | ✓                 |
| OleDb              | ✓        |           |     | ✓         | ✓                 |
| SmoServer          | ✓        |           |     | ✓         |                   |
| Smtp               | ✓        |           |     | ✓         |                   |
| SqlMobile          |          | ✓         | ✓   |           |                   |
| Wmi                | ✓        |           |     |           |                   |
|||||||

## Validate sources and destinations
The following third-party sources and destinations are not supported:

-   Oracle Source and Destination by Attunity
-   Teradata Source and Destination by Attunity
-   SAP BI Source and Destination

## Validate tasks and components

### Execute Process Task

Validation raises a warning if a command points to a local file with an absolute path, or to a file with a UNC path. These paths may cause execution on Azure to fail.

### Script Task and Script Component

Validation raises a warning if a package contains a script task or a script component, which may reference or call unsupported assemblies. These references or calls may cause execution to fail.

### Other components

The Orc format is not supported in the HDFS Destination and the Azure Data Lake Store Destination.

## Next steps
To learn how to schedule package execution on Azure, see [Schedule the execution of an SSIS package on Azure](ssis-azure-schedule-packages.md).