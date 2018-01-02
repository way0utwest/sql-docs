---
title: "What&#39;s new in Machine Learning Services | Microsoft Docs"
ms.date: "11/16/2017"
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
ms.assetid: 6aff043a-8b37-4f3f-9827-10a671e1ad1c
caps.latest.revision: 36
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
ms.workload: "On Demand"
---
# What's new in Machine Learning Services in SQL Server

In SQL Server 2016, Microsoft introduced SQL Server R Services, a feature that supports enterprise-scale data science, by integrating the R language with the SQL Server database engine.

In SQL Server 2017, database-integrated machine learning became even more powerful, with addition of support for the popular Python language. Along with the support for new languages comes a new name: **Machine Learning Services (In-Database)**.

Catch the latest announcement here! [Python in SQL Server 2017: enhanced in-database machine learning](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## What's new in SQL Server 2017

Machine Learning Server in SQL Server provides comprehensive support for building and deploying machine learning solutions in either R or Python. Here are the highlights of this release:

### What's new in Cumulative Update 1 for SQL Server 2017

You can now upgrade your Python and R components to Machine Learning Server 9.2.1.24. This release features many enhancements to **revoscalepy** and **RevoScaleR**, including performance improvements.

### In-database Python integration

You can run Python in stored procedures, or execute Python remotely using the SQL Server computer as the compute context. This integration opens up new avenues for the vast community of Python developers and data scientists to use the power of SQL Server.

SQL Server developers gain access to the extensive Python libraries from the open source ecosystem, including popular frameworks such as scikit-learn, TensorFlow, Caffe, and Theano/Keras. And be sure to explore innovations from Microsoft such as **revoscalepy** and **microsoftml**!

Running Python in-database isn't just about machine learning, by the way. There are a myriad of other potential applications for integrating Python with SQL, and using the power of each language to deliver more intelligent, powerful solutions.

+ **revoscalepy**

    This release includes the final version of **revoscalepy**, which supplies Python equivalents of the algorithms in RevoScaleR. You can create Python models for linear and logistic regressions, decision trees, boosted trees, and random forests, all parallelizable, and capable of being run in remote compute contexts.

    For more information, see [What is revoscalepy](python/what-is-revoscalepy.md).

+ Remote compute contexts for Python

    This release supports use of multiple data sources and remote compute contexts. The data scientist or developer can execute Python code on a remote SQL Server, to explore data or build models without moving data. Use of remote compute contexts requires **revoscalepy**.

+ Python support in Microsoft Machine Learning Server (Standalone)

    [!INCLUDE[sscurrent-md](../includes/sscurrent-md.md)] includes the option to install a standalone version of the Microsoft Machine Learning Server. By using Machine Learning Server, you can distribute and scale R or Python code without using SQL Server.

### Linux support

Machine learning using R or Python in-database is not currently supported in SQL Server on Linux. Look for announcements in a later release.

However, on Linux you can perform [native scoring](sql-native-scoring.md) using the T-SQL PREDICT function. Native scoring lets you score from a pretrained model very fast, without calling or even requiring an R runtime. This means you can use SQL Server on Linux to generate predictions very fast, to serve client applications.

### New algorithms

The **MicrosoftML** package for both R and Python contains state-of-the-art machine learning algorithms and data transformation that can be scaled or run in remote compute contexts. Algorithms include customizable deep neural networks, fast decision trees and decision forests, linear regression, and logistic regression. The MicrosoftML package comes with both R and Python interfaces.

For more information, see [Introduction to MicrosoftML](using-the-microsoftml-package.md) and [microsoftml for Python](https://docs.microsoft.com/machine-learning-server/python-reference/microsoftml/microsoftml-package).

### Operationalization

This release contains multiple options and features to help you deploy and distribute machine learning tasks:

+ Deploy and integrate machine Python solutions, using T-SQL

    The integration of Python with T-SQL means that you can call any Python code using `sp_execute_external_script`. This secure infrastructure enables enterprise-grade deployment of Python models and scripts that can be called from an application using a simple stored procedure. Additional performance is by streaming data from SQL to Python processes and MPI ring parallelization.

+ **mrsdeploy** for Python

    The **mrsdeploy** package for [!INCLUDE[rsql-platform-md](../includes/rsql-platformnew-md.md)] and [!INCLUDE[rsql-platformnew-md](../includes/rsql-platformnew-md.md)] supports deployment of Python models and scripts as web services. For an example of how it works, see [Publish and consume Python code](python/publish-consume-python-code.md).

+ Performance

    Microsoft has pushed the boundaries of performance for scoring. With in-database scoring, we processed a million rows per second using R models. In this release, new features for **realtime scoring** and **native scoring** support better performance in single-row and batch scoring.

### Realtime scoring and native scoring

Realtime scoring relies on native C++ libraries to read a model stored in an optimized binary format, and then generate predictions without having to call the R runtime. This makes scoring operations much faster.

Additionally, this release of [!INCLUDE[sscurrent-md](../includes/sscurrent-md.md)] includes a native T-SQL function for fast scoring that can be run on any edition of SQL Server, even on Linux. The function requires no installation of R or extra configuration. This means you can train a model elsewhere, save it in SQL Server, and then perform scoring without ever calling R. This feature is referred to as _native scoring_.

  - Native scoring is available only in [!INCLUDE[sscurrent-md](../includes/sscurrent-md.md)]. It uses a T-SQL function that can run in any edition of SQL Server, including Linux.
 - Realtime scoring is supported in [!INCLUDE[sscurrent-md](../includes/sscurrent-md.md)], and in Microsoft Machine Learning Server. You can run a  stored procedure or perform realtime scoring from R code.
 - Realtime scoring is also available for SQL Server 2016, if the instance is upgraded to the latest release of [!INCLUDE[rsql-platform-md](../includes/rsql-platform-md.md)].

For more information, see these articles:

 + [Realtime scoring](real-time-scoring.md)
 + [Native scoring](sql-native-scoring.md)
 + [How to perform realtime scoring or native scoring](r/how-to-do-realtime-scoring.md)

### Upgrade your machine learning experience and get pre-trained models

If you installed an earlier version of SQL Server 2016 R Services, you can now upgrade to the latest version by switching your server to use the Modern Software Lifecycle policy. By doing so, you can take advantage of a faster release cycle for R and automatically upgrade all R components. For more information, see [What's new in Machine Learning Server](https://docs.microsoft.com/machine-learning-server/whats-new-in-machine-learning-server).

The installer also offers the option to install a collection of pre-trained models in binary format. These models support machine learning in scenarios such as image recognition, where it might be difficult for customers to find large datasets to train a model. After you install one of the pre-trained models, you can use it for prediction on your own data without the time and expense involved in training such a large and complex model.

For more information, see [Install pre-trained models in SQL Server](r/install-pretrained-models-sql-server.md)

### Package management

This release includes many improvements in package management for SQL Server. These include:

- Database roles to help the DBA manage packages and assign permissions to install packages
- The CREATE EXTERNAL LIBRARY statement in T-SQL, to help DBAs manage packages without needing to know R
- A rich set of R functions to help install, remove, or list packages owned by users

For more information, see [Package management](r/r-package-management-for-sql-server-r-services.md).

### Get started

+ [Set up Python in SQL Server Machine Learning Services](../advanced-analytics/python/setup-python-machine-learning-services.md)

+ [Set up R in SQL Server Machine Learning Services](r/set-up-sql-server-r-services-in-database.md)

+ [Machine learning tutorials and samples](tutorials/machine-learning-services-tutorials.md)
