---
title: "SQL Server Machine Learning Services Tutorials | Microsoft Docs"
ms.date: "12/14/2017"
ms.reviewer: 
ms.suite: sql
ms.prod: machine-learning-services
ms.prod_service: machine-learning-services
ms.component: 
ms.technology: 
  - "r-services"
ms.tgt_pltfrm: ""
ms.topic: "tutorial"
applies_to: 
  - "SQL Server 2016"
  - "SQL Server 2017"
dev_langs: 
  - "Python"
  - "R"
ms.assetid: 5ccc75f6-6703-47d9-b879-9a740569b45e
caps.latest.revision: 32
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
ms.workload: "On Demand"
---
# Tutorials for SQL Server Machine Learning Services

This article provides a comprehensive list of the tutorials, demos, and sample applications that use machine learning features in SQL Server 2016 or SQL Server 2017. Start here to learn how to run R or Python from T-SQL, how to use remote and local compute contexts, and how to optimize your R and Python code for a SQL production environment.

## Start here

+ [Python tutorials](../tutorials/sql-server-python-tutorials.md)

+ [R tutorials](../tutorials/sql-server-r-tutorials.md)

For more information about requirements and how to get set up, see [Prerequisites](#bkmk_prerequisites).

## Samples and solutions

+ [Samples](#bkmk_samples) 

    These real-world scenarios from the SQL Server development team demonstrate how to embed machine learning in applications. All samples include code that you can download, modify, and use in production.

+ [Solutions](#bkmk_solutions) 

    Templates from the Microsoft Data Science team are customizable, to get you started fast with machine learning. Each solution is tailored to a specific task or industry problem. Most of the solutions are designed to run either in SQL Server, or in a cloud environment such as Azure Machine Learning. Other solutions can run on Linux or in Spark or Hadoop clusters, by using Microsoft R Server or Machine Learning Server.

### <a name ="bkmk_samples"></a>SQL Server product samples

These samples and demos provided by the SQL Server and R Server development team highlight ways that you can use embedded analytics in real-world applications.

+ [Perform customer clustering using R and SQL Server](https://microsoft.github.io/sql-ml-tutorials/R/customerclustering/)

  Use unsupervised learning to segment customers based on sales data. This example uses the scalable rxKmeans algorithm from Microsoft R to build the clustering model. 
  
  Applies to: SQL Server 2016 or SQL Server 2017

+ [NEW! Perform customer clustering using Python and SQL Server](https://microsoft.github.io/sql-ml-tutorials/python/customerclustering/)

    Learn how to use the Kmeans algorithm to perform unsupervised clustering of customers. This example uses the Python language in-database.
    
    Applies to: SQL Server 2017

+ [Build a predictive model using R and SQL Server](https://microsoft.github.io/sql-ml-tutorials/R/rentalprediction)

  Learn how a ski rental business might use machine learning to predict future rentals, which helps the business plan and staff to meet future demand. This example uses the Microsoft algorithms to build logistic regression and decision trees models. 
  
  Applies to: SQL Server 2016 or SQL Server 2017

+ [Build a predictive model using Python and SQL Server](https://microsoft.github.io/sql-ml-tutorials/python/rentalprediction/)

   Build the ski rental analysis application using Python, to help plan for future demand. This example uses the new Python library, **revoscalepy**, to create a linear regression model.
   
   Applies to: SQL Server 2017

+ [How to use Tableau with SQL Server Machine Learning Services](https://blogs.msdn.microsoft.com/mlserver/2017/12/14/how-to-use-tableau-with-sql-server-machine-learning-services-with-r-and-python/)

    Analyze social media and create Tableau graphs, using SQL Server and R.

### <a name="bkmk_solutions"></a>Solution templates

The Microsoft Data Science Team has provided solution templates that can be used to jump-start solutions for common scenarios. All code is provided, along with instructions on how to train and deploy a model for scoring using SQL Server stored procedures.

+ [Fraud detection](https://gallery.cortanaanalytics.com/Tutorial/Online-Fraud-Detection-Template-with-SQL-Server-R-Services-1)
+ [Custom churn prediction](https://gallery.cortanaanalytics.com/Tutorial/Customer-Churn-Prediction-Template-with-SQL-Server-R-Services-1)
+ [Predictive maintenance](https://gallery.cortanaanalytics.com/Tutorial/Predictive-Maintenance-Template-with-SQL-Server-R-Services-1)
+ [Predict hospital length of stay](https://gallery.cortanaintelligence.com/Solution/Predicting-Length-of-Stay-in-Hospitals-1)

For more information, see [Machine Learning Templates with SQL Server 2016 R Services](https://blogs.technet.microsoft.com/machinelearning/2016/03/23/machine-learning-templates-with-sql-server-2016-r-services/).

## More resources and reading

+ [Why did we build it?](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2017/01/10/sql-server-r-services-why-did-we-build-it/)

    Want to know the real story behind R Services? Read this article from the development and PM team that explains the origin and goals of SQL Server R Services.

+ [Tutorials and sample data for Microsoft R](https://docs.microsoft.com/machine-learning-server/r/tutorial-introduction)

    Learn about Microsoft R, and what the RevoScaleR package offers in this collection of quick tutorials. Learn how to write R code once and deploy anywhere, using RevoScaleR data sources and remote compute contexts.

+ [Get started with MicrosoftML](https://docs.microsoft.com/machine-learning-server/r/concept-what-is-the-microsoftml-package)

  Learn how to use the new algorithms in the MicrosoftML package for advanced modeling and scalable data transformations, optimized for multiple compute contexts.

## <a name="bkmk_Prerequisites"></a>Prerequisites

To run these tutorials, you must download and install the SQL Server machine learning components, as described here:

+ [Set up SQL Server 2017 Machine Learning Services or SQL Server 2016 R Services](../r/set-up-sql-server-r-services-in-database.md)
+ [Set up SQL Server 2017 Python Services](../python/setup-python-machine-learning-services.md)

With SQL Server 2017, you can install either R or Python, or both. Otherwise the overall setup process, architecture, and requirements are the same.

After running SQL Server setup, don't forget these important steps:

1. Enable the external script execution feature by running `sp_configure 'external scripts enabled', 1`. Follow the instructions to reconfigure and restart SQL Server.
2. Ensure that the Launchpad service is running, and that the Launchpad worker accounts can connect to the SQL Server instance.
3. Review the permissions associated with the users who must run R or Python scripts. Regardless of whether you use SQL logins or Windows user accounts, the user must have permission to run R or Python scripts, and must be able to connect to the instance. Depending on the tutorial, the user might also require permission to write data, create database objects, or do a bulk import of data.

For details, see this article for some common setup and configuration issues: [Troubleshooting Machine Learning Services](../machine-learning-troubleshooting-faq.md)

> [!NOTE]
> You cannot run these tutorials using another open source R or Python tool. Both your development environment and the SQL Server computer with machine learning must have the R or Python libraries provided by Microsoft, which support integration with SQL Server and use of remote compute contexts.
