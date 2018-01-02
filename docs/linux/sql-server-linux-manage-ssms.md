---
title: Use SSMS to Manage SQL Server on Linux | Microsoft Docs
description: 
author: sanagama 
ms.author: sanagama 
manager: jhubbard
ms.date: 08/23/2017
ms.topic: article
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: sql-linux
ms.suite: "sql"
ms.technology: database-engine
ms.assetid: b2fcf858-21c3-462a-8d49-50c85647d092
ms.custom: ""
ms.workload: "On Demand"
---
# Use SQL Server Management Studio on Windows to manage SQL Server on Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

This topic introduces [SQL Server Management Studio (SSMS)](../ssms/sql-server-management-studio-ssms.md) and walks you through a couple of common tasks. SSMS is a Windows application, so use SSMS when you have a Windows machine that can connect to a remote SQL Server instance on Linux.

[SQL Server Management Studio (SSMS)](../ssms/sql-server-management-studio-ssms.md) is part of a suite of SQL tools that Microsoft offers free of charge for your development and management needs. SSMS is an integrated environment to access, configure, manage, administer, and develop all components of SQL Server running on-premises or in the cloud, on Linux, Windows or Docker on macOS and Azure SQL Database and Azure SQL Data Warehouse. SSMS combines a broad group of graphical tools with a number of rich script editors to provide access to SQL Server to developers and administrators of all skill levels.

SSMS offers a broad set of development and management capabilities for SQL Server, including tools to:

- Configure, monitor and administer single or multiple instances of SQL Server
- Deploy, monitor, and upgrade data-tier components such as databases and data warehouses
- Backup and restore databases
- Build and execute T-SQL queries and scripts and see results
- Generate T-SQL scripts for database objects
- View and edit data in databases
- Visually design T-SQL queries and database objects such as views, tables and stored procedures

See [Use SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/ms174173.aspx) for more information.

## Install the newest version of SQL Server Management Studio (SSMS)

When working with SQL Server, you should always use the most recent version of SQL Server Management Studio (SSMS). The latest version of SSMS is continually updated and optimized and currently works with SQL Server 2017 on Linux. To download and install the latest version, see [Download SQL Server Management Studio](../ssms/download-sql-server-management-studio-ssms.md). To stay up-to-date, the latest version of SSMS prompts you when there is a new version available to download. 

## Before you begin
- See [Use SSMS on Windows to connect to SQL Server on Linux](sql-server-linux-develop-use-ssms.md) for how to Connect and Query using SSMS
- Read the [Known Issues](sql-server-linux-release-notes.md) for SQL Server 2017 on Linux

## Create and manage databases
While connected to the *master* database, you can create databases on the server and modify or drop existing databases. The following steps describe how to accomplish several common database management tasks through Management Studio. To perform these tasks, make sure you are connected to the *master* database with the server-level principal login that you created when you set up SQL Server 2017 on Linux.

### Create a new database

1. Start SSMS and connect to your server in SQL Server 2017 on Linux

2. In Object Explorer, right-click on the *Databases* folder, and then click *New Database..."

3. In the *New Database* dialog, enter a name for your new database, and then click *OK*

The new database is successfully created in your server. If you prefer to create a new database using T-SQL, then see [CREATE DATABASE (SQL Server Transact-SQL)](../t-sql/statements/create-database-sql-server-transact-sql.md).

### Drop a database

1. Start SSMS and connect to your server in SQL Server 2017 on Linux

2. In Object Explorer, expand the *Databases* folder to see a list of all the database on the server.

3. In Object Explorer, right-click on the database you wish to drop, and then click *Delete*

4. In the *Delete Object* dialog, check *Close existing connections* and then click *OK*

The database is successfully dropped from your server. If you prefer to drop a database using T-SQL, then see [DROP DATABASE (SQL Server Transact-SQL)](../t-sql/statements/drop-database-transact-sql.md).

## Use Activity Monitor to see information about SQL Server activity

The [Activity Monitor](../relational-databases/performance-monitor/activity-monitor.md) tool is built-in into SQL Server Management Studio (SSMS) and displays information about SQL Server processes and how these processes affect the current instance of SQL Server.

1. Start SSMS and connect to your server in SQL Server 2017 on Linux

2. In Object Explorer, right-click the *server* node, and then click *Activity Monitor*

Activity Monitor shows expandable and collapsible panes with information about the following:
- Overview
- Processes
- Resource Waits
- Data File I/O
- Recent Expensive Queries
- Active Expensive Queries

When a pane is expanded, Activity Monitor queries the instance for information. When a pane is collapsed, all querying activity stops for that pane. You can expand one or more panes at the same time to view different kinds of activity on the instance.

## See also
- [Use SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/ms174173.aspx)
- [Export and Import a database with SSMS](sql-server-linux-migrate-ssms.md)
- [Tutorial: SQL Server Management Studio](https://msdn.microsoft.com/en-us/library/bb934498.aspx)
- [Tutorial: Writing Transact-SQL Statements](../t-sql/tutorial-writing-transact-sql-statements.md)
- [Server Performance and Activity Monitoring](../relational-databases/performance/server-performance-and-activity-monitoring.md)
