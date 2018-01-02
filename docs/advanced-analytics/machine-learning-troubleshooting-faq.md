---
title: "Troubleshooting and FAQ for machine learning in SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "06/16/2017"
ms.prod: "machine-learning-services"
ms.prod_service: "machine-learning-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
ms.workload: "Inactive"
---

# Troubleshoot machine learning

This article provides troubleshooting information related to setup and configuration of machine learning features in SQL Server. The information includes links to setup guides, known issues, and release notes. Other articles linked to from this article provide advice about performance optimization for machine learning solutions in SQL Server.

Use this page as a starting point for finding known issues, common setup questions, and procedures for troubleshooting.

**Applies to:** SQL Server 2016 R Services, SQL Server 2017 Machine Learning Services (R and Python)

## Known issues

The following articles list known issues with the current release, or describe issues with previous releases:

+ [Known issues for R Services](../advanced-analytics/known-issues-for-sql-server-machine-learning-services.md)
+ [SQL Server 2016 release notes](../sql-server/sql-server-2016-release-notes.md)
+ [SQL Server 2017 release notes](../sql-server/sql-server-2017-release-notes.md)

## Troubleshooting prerequisites

If you have encountered an error, or need to understand an issue in your environment, it is important that you collect related information systematically. This information includes the version, edition, security context, and execution context.

The following article provides a list of information that facilitates self-help troubleshooting, or a request for technical support.

+ [Data collection for machine learning troubleshooting](data-collection-ml-troubleshooting-process.md)

## Setup and configuration guides

Start here if you have not set up machine learning with SQL Server, or if you want to add the feature:

+ [Set up R Services or Machine Learning Services with R](../advanced-analytics/r/set-up-sql-server-r-services-in-database.md)
+ [Set up Machine Learning Services with Python](../advanced-analytics/python/setup-python-machine-learning-services.md)
+ [Setup FAQ](../advanced-analytics/r/upgrade-and-installation-faq-sql-server-r-services.md)
+ [Use SqlBindR to upgrade an instance of R services](../advanced-analytics/r/use-sqlbindr-exe-to-upgrade-an-instance-of-sql-server.md)

The following articles describe the additional steps required for offline setup of machine learning features in SQL Server:

+ [Unattended installation of R Services](../advanced-analytics/r/unattended-installs-of-sql-server-r-services.md) 
+ [Unattended installation of Machine Learning Services with Python](../advanced-analytics/python/unattended-installs-of-sql-server-python-services.md)

If you need to install the machine learning features on a computer with no Internet connection, use the links in this article to download the R and Python components before beginning setup:

+ [Installing machine learning components without Internet access](../advanced-analytics/r/installing-ml-components-without-internet-access.md)

### Configuration

The following articles contain information about defaults, and how to customize the configuration for machine learning on an instance:

+ [Modify the user account pool for SQL Server R Services](../advanced-analytics/r/modify-the-user-account-pool-for-sql-server-r-services.md)  
+ [Configure and manage advanced analytics extensions](../advanced-analytics/r/configure-and-manage-advanced-analytics-extensions.md)  
+ [How to create a resource pool](r/how-to-create-a-resource-pool-for-r.md)
+ [Optimization for R workloads](r/operationalizing-your-r-code.md)

## Related tools and services

+ [Set up Microsoft Machine Learning Server Standalone](../advanced-analytics/r/create-a-standalone-r-server.md)
+ [Set up R Server on an Azure VM](../advanced-analytics/r/provision-the-r-server-only-sql-server-2016-enterprise-vm-on-azure.md)
+ [Install R Server for Windows](https://msdn.microsoft.com/microsoft-r/rserver-install-windows)
+ [Get R Tools for Visual Studio](https://www.visualstudio.com/vs/rtvs/)
