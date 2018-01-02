---
title: "SSIS How to Create an ETL Package | Microsoft Docs"
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
ms.topic: "get-started-article"
applies_to: 
  - "SQL Server 2016"
helpviewer_keywords: 
  - "SSIS, tutorials"
  - "packages [Integration Services], tutorials"
  - "Integration Services, tutorials"
  - "SQL Server Integration Services, tutorials"
  - "logs [Integration Services], tutorials"
  - "walkthroughs [Integration Services]"
ms.assetid: d6d5bb1f-4cb1-4605-9cd6-f60b858382c4
caps.latest.revision: 38
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "Active"
---
# SSIS How to Create an ETL Package

 > For content related to previous versions of SQL Server, see [SSIS Tutorial: Creating a Simple ETL Package](https://msdn.microsoft.com/library/ms169917(SQL.120).aspx).

[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (SSIS) is a platform for building high-performance data integration solutions, including extraction, transformation, and load (ETL) packages for data warehousing. SSIS includes graphical tools and wizards for building and debugging packages; tasks for performing workflow functions such as FTP operations, executing SQL statements, and sending e-mail messages; data sources and destinations for extracting and loading data; transformations for cleaning, aggregating, merging, and copying data; a management service, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for administering package execution and storage; and application programming interfaces (APIs) for programming the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model.  
  
In this tutorial, you learn how to use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to create a simple [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package. The package that you create takes data from a flat file, reformats the data, and then inserts the reformatted data into a fact table. In following lessons, the package is expanded to demonstrate looping, package configurations, logging, and error flow.  
  
When you install the sample data that the tutorial uses, you also install the completed versions of the packages that you create in each lesson of the tutorial. By using the completed packages, you can skip ahead and begin the tutorial at a later lesson if you like. If this tutorial is your first time working with packages or the new development environment, we recommend that you begin with Lesson1.  
  
## What You Learn  
The best way to become acquainted with the new tools, controls, and features available in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to use them. This tutorial walks you through [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to create a simple ETL package that includes looping, configurations, error flow logic, and logging.  
  
## Requirements  
This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to the new features available in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
To use this tutorial, your system must have the following components installed:  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with the **AdventureWorksDW2012** database. To enhance security, the sample databases are not installed by default. To download the **AdventureWorksDW2012** database, see [Adventure Works for SQL Server 2012](http://go.microsoft.com/fwlink/?LinkId=275026).  
  
    > [!IMPORTANT]  
    > When you attach the database (\*.mdf file), [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by default searches for an .ldf file. Remove the .ldf file manually before you click OK in the **Attach Databases** dialog box.  
    >   
    > For more information about attaching databases, see [Attach a Database](../relational-databases/databases/attach-a-database.md).  
  
-   Sample data. The sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages. To download the sample data and the lesson packages, do the following things.  
  
    1.  Navigate to [Integration Services Product Samples](http://go.microsoft.com/fwlink/?LinkId=275027)  
  
    2.  Click the **DOWNLOADS** tab.  
  
    3.  Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.  
  
## Lessons in This Tutorial  
[Lesson 1: Create a Project and Basic Package with SSIS](../integration-services/lesson-1-create-a-project-and-basic-package-with-ssis.md)  
In this lesson, you create a simple ETL package that extracts data from a single flat file, transforms the data using lookup transformations and finally loads the result into a fact table destination.  
  
[Lesson 2: Adding Looping with SSIS](../integration-services/lesson-2-adding-looping-with-ssis.md)  
In this lesson, you expand the package you created in Lesson 1 to take advantage of new looping features to extract multiple flat files into a single data flow process.  
  
[Lesson 3: Add Logging with SSIS](../integration-services/lesson-3-add-logging-with-ssis.md)  
In this lesson, you expand the package you created in Lesson 2 to take advantage of new logging features.  
  
[Lesson 4: Add Error Flow Redirection with SSIS](../integration-services/lesson-4-add-error-flow-redirection-with-ssis.md)  
In this lesson, you expand the package you created in lesson 3 to take advantage of new error output configurations.  
  
[Lesson 5: Add SSIS Package Configurations for the Package Deployment Model](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
In this lesson, you expand the package you created in Lesson 4 to take advantage of new package configuration options.  
  
[Lesson 6: Using Parameters with the Project Deployment Model in SSIS](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
In this lesson, you expand the package you created in Lesson 5 to take advantage of using new parameters with the project deployment model.  
  
  
  
