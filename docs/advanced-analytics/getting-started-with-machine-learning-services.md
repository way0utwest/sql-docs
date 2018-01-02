---
title: "Getting started with machine learning in SQL Server| Microsoft Docs"
ms.custom: ""
ms.date: "12/20/2017"
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
manager: "cgronlund"
ms.workload: "On Demand"
---
# Getting started with machine learning in SQL Server

Microsoft provides an integrated, scalable set of machine learning solutions for both on-premises and the cloud:

+ **Integrated**, because you can run R or Python in SQL Server. This lets you easily merge enterprise processes for ETL and reporting with data science tasks such as feature engineering, model creation, and scoring.
+ **Scalable**, because the data scientist can develop and test a solution on a laptop, and then deploy it to multiple platforms for distributed or parallel processing of key operations such as model training and scoring. Supported platforms include SQL Server on Windows, Hadoop, and Spark.

This article provides links to resources for each product in the Microsoft Machine Learning platform.

## Machine learning in SQL Server

+ SQL Server 2017

  Beginning with SQL Server 2017, you can now use Python code in SQL Server. To reflect the broader support for solutions in multiple languages (with more to come!), and the name was changed to [!INCLUDE[rsql-productnamenew-md](../includes/rsql-productnamenew-md.md)]. Now you can automate machine learning tasks by using SQL tools to run either R or Python code. Or, use the SQL Server computer as the _compute context_ for jobs launched from a remote development environment.

    + [Architecture Overview for Python in SQL Server](/python/architecture-overview-sql-server-python.md)
    + [Set up SQL Server R Services or Machine Learning Services](../advanced-analytics/r/set-up-sql-server-r-services-in-database.md)

+ SQL Server 2016

  SQL Server 2016 supports running R code in SQL Server using stored procedures. This makes it easy to automate machine learning tasks by using SQL tools. Or, you can run R code from a remote laptop or R development environment, while using the SQL Server computer as the _compute context_.

  This integration provides security for your data and lets you manage and balance resources used by R.

    + [Getting Started wth SQL Server R Services](r/getting-started-with-sql-server-r-services.md)
    + [Set up SQL Server R Services or Machine Learning Services](../advanced-analytics/r/set-up-sql-server-r-services-in-database.md)

## Microsoft Machine Learning Server (Microsoft R Server)

The option to install [!INCLUDE[rsql-platformnew-md](../includes/rsql-platformnew-md.md)] is provided in SQL Server 2017 to support enterprise customers who want to run distributed, scalable machine learning jobs, but who don't need the integration with the SQL Server database engine, such as the use of SQL compute contexts.

In SQL Server 2016, use the option to install [!INCLUDE[rsql-platform-md](../includes/rsql-platformnew-md.md)].
  
  + [Welcome to Machine Learning Server](https://docs.microsoft.com/machine-learning-server/what-is-machine-learning-server)
  
You can also install [!INCLUDE[rsql-platform-md](../includes/rsql-platform-md.md)] or [!INCLUDE[rsql-platformnew-md](../includes/rsql-platformnew-md.md)] through platform-specific installers:

  + [Install on Windows](https://docs.microsoft.com/machine-learning-server/install/machine-learning-server-windows-install)
  + [Install on Linux](https://docs.microsoft.com/machine-learning-server/install/machine-learning-server-linux-install)
  + [Install on Hadoop](https://docs.microsoft.com/machine-learning-server/install/machine-learning-server-hadoop-install)

> [!IMPORTANT]
> If you want to run Python using R Server, be sure to install the latest version, [!INCLUDE[rsql-platformnew-md](../includes/rsql-platformnew-md.md)], which is available only through [!INCLUDE[sscurrent-md](../includes/sscurrent-md.md)] setup:
> 
>    + [Set up Microsoft R Server or Machine Learning Server](../advanced-analytics/r/create-a-standalone-r-server.md)

## Related products

+ [Set up a data science client](../advanced-analytics/r/set-up-a-data-science-client.md)

  If you already installed one of the machine learning server products, this article provides information about how to set up a separate computer for development and testing of solutions, including tools and required libraries.

+ [Data Science Virtual Machine](../advanced-analytics/r/provision-the-r-server-only-sql-server-2016-enterprise-vm-on-azure.md)

  Jump-start your entry into machine learning by getting this complete machine learning solution from the Azure Marketplace. The data science virtual machine (frequently shortened to "DSVM") includes SQL Server, Microsoft Machine Learning Server, and all development tools.
  
  The latest version of the Data Science Virtual Machine (DSVM) runs on Windows 2016 Preview Edition, to provide the clean customizable look of Windows 10. It comes pre-configured with NVIDIA drivers, CUDA Toolkit 8.0, and the NVIDIA cuDNN library for GPU workloads.

## Resources for learning

+ [Machine learning tutorials](../advanced-analytics/tutorials/machine-learning-services-tutorials.md)

  Start here to find a list of all resources for learning about machine learning solutions using SQL Server 2016 and SQL Server 2017.

### R tutorials

+ [SQL Server R tutorials](../advanced-analytics/tutorials/sql-server-r-tutorials.md)

   Learn how to run R in SQL Server, create and use remote compute contexts, or perform simulations in R using SQL Server.
   
   Includes "all code provided" tutorials so that you can run a complete R solution from SQL Server Management Studio, without ever opening an R IDE!

+ [Explore R and ScaleR in 25 short functions](https://docs.microsoft.com/r-server/r/tutorial-r-to-revoscaler)

   New to R? Wondering how Microsoft R (or RevoScaleR) compares to standard R? See these quick-starts for R Server and Machine Learning Server.

### Python tutorials

+ [SQL Server Python tutorials](../advanced-analytics/tutorials/sql-server-r-tutorials.md)

  Learn how to run Python in [!INCLUDE[ssnoversion](../includes/ssnoversion.md)]. Build a model using Python and use it to score SQL Server data.

   An end-to-end solution for SQL developers provides all the code you need to run Python from SQL Server Management Studio.

+ [Publish and consume Python Code](../advanced-analytics/python/publish-consume-python-code.md)

  This walkthrough comes with all code needed to deploy a model to a web service using Machine Learning Server.

### Product samples with code

These solutions from the SQL Server development team run in either R or Python, and demonstrate common scenarios for integrating machine learning with business applications.

+ [Build an intelligent app with SQL Server and R](https://microsoft.github.io/sql-ml-tutorials/R/rentalprediction)

+ [Build an intelligent app with SQL Server and Python](https://microsoft.github.io/sql-ml-tutorials/python/rentalprediction/)

### Data science solution templates

The solution templates from the Microsoft Data Science team represent complete sample solutions tailored for specific industries or scenarios. They are intended to serve as building blocks to help you implement a solution fast, or to demonstrate best practices. Each template includes sample data and customizable code.

+ [Solution templates](../advanced-analytics/tutorials/data-science-scenarios-and-solution-templates.md)

## Next steps

[Get started with SQL Server Machine Learning Services](../advanced-analytics/r/getting-started-with-sql-server-r-services.md)

[Get Started with Microsoft Machine Learning Server](../advanced-analytics/r/getting-started-with-microsoft-r-server-standalone.md)
