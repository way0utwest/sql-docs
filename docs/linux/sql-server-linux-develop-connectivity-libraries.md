---
title: Connectivity libraries and frameworks | Microsoft Docs
description: Lists the connectivity drivers that client apps can use from various languages to connect to Microsoft SQL Server running on-premises or in the cloud, on Linux, Windows or Docker and also to Azure SQL Database and Azure SQL Data Warehouse. 
author: sanagama 
ms.author: sanagama 
manager: jhubbard
ms.date: 03/17/2017
ms.topic: article
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: sql-linux
ms.suite: "sql"
ms.custom: ""
ms.technology: database-engine
ms.assetid: 80efe5ff-09ba-48a0-ac93-a91d62cff47c
ms.workload: "Inactive"
---
# Connectivity libraries and frameworks for Microsoft SQL Server

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Check out our [Getting Started Tutorials](http://aka.ms/sqldev) to quickly get started with programming languages such as C#, Java, Node.js, PHP and Python and build an app using SQL Server on Linux or Windows or Docker on macOS.

The table below lists connectivity libraries or *drivers* that client applications can use from a variety of languages to connect to and use Microsoft SQL Server running on-premises or in the cloud, on Linux, Windows or Docker and also to Azure SQL Database and Azure SQL Data Warehouse. 

| Language | Platform | Additional resources | Download | Get Started |
| :-- | :-- | :-- | :-- | :-- |
| C# | Windows, Linux, macOS | [Microsoft ADO.NET for SQL Server](http://msdn.microsoft.com/library/mt657768.aspx) | [Download](https://msdn.microsoft.com/vstudio/aa496123.aspx) | [Get Started](https://www.microsoft.com/en-us/sql-server/developer-get-started/csharp/ubuntu)
| Java | Windows, Linux, macOS | [Microsoft JDBC Driver for SQL Server](http://msdn.microsoft.com/library/mt484311.aspx) | [Download](http://go.microsoft.com/fwlink/?LinkId=245496) |  [Get Started](https://www.microsoft.com/en-us/sql-server/developer-get-started/java/ubuntu)
| PHP | Windows, Linux, macOS| [PHP SQL Driver for SQL Server](http://msdn.microsoft.com/library/dn865013.aspx) | Operating System: <br/> \* [Windows](https://www.microsoft.com/download/details.aspx?id=20098) <br/> \* [Linux](https://github.com/Microsoft/msphpsql/tree/dev#install-unix) <br/> \* [macOS](https://github.com/Microsoft/msphpsql/tree/dev#install-unix) |  [Get Started](https://www.microsoft.com/en-us/sql-server/developer-get-started/php/ubuntu)
| Node.js | Windows, Linux, macOS | [Node.js Driver for SQL Server](../connect/node-js/node-js-driver-for-sql-server.md) |  [Get Started](https://www.microsoft.com/en-us/sql-server/developer-get-started/node/ubuntu)
| Python | Windows, Linux, macOS | [Python SQL Driver](../connect/python/python-driver-for-sql-server.md) <br/> \* [pyodbc](http://msdn.microsoft.com/library/mt763257.aspx) |  [Get Started](https://www.microsoft.com/en-us/sql-server/developer-get-started/python/ubuntu)
| Ruby | Windows, Linux, macOS | [Ruby Driver for SQL Server](../connect/ruby/ruby-driver-for-sql-server.md) | [Get Started](https://www.microsoft.com/en-us/sql-server/developer-get-started/ruby/ubuntu)
| C++ | Windows, Linux, macOS | [Microsoft ODBC Driver for SQL Server](https://msdn.microsoft.com/en-us/library/mt654048(v=sql.1).aspx) | [Download](https://msdn.microsoft.com/en-us/library/mt654048(v=sql.1).aspx) |  

The table below lists a few examples of Object Relational Mapping (ORM) frameworks and web frameworks that client applications can use with Microsoft SQL Server running on-premises or in the cloud, on Linux, Windows or Docker and also to Azure SQL Database and Azure SQL Data Warehouse. 

| Language | Platform | ORM(s) |
| :-- | :-- | :-- |
| C# | Windows, Linux, macOS | [Entity Framework](https://docs.microsoft.com/en-us/ef)<br>[Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/index) |
| Java | Windows, Linux, macOS |[Hibernate ORM](http://hibernate.org/orm)|
| PHP | Windows, Linux | [Laravel (Eloquent)](https://laravel.com/docs/5.0/eloquent) |
| Node.js | Windows, Linux, macOS | [Sequelize ORM](http://docs.sequelizejs.com) |
| Python | Windows, Linux, macOS |[Django](https://www.djangoproject.com/) |
| Ruby | Windows, Linux, macOS | [Ruby on Rails](http://rubyonrails.org/) |

## Related links
- [SQL Server Drivers](http://msdn.microsoft.com/library/mt654049.aspx) for connecting from client applications
