---
title: Get started with SQL Server 2017 on SUSE Linux Enterprise Server | Microsoft Docs
description:  This quickstart shows how to install SQL Server 2017 on SUSE Linux Enterprise Server and then create and query a database with sqlcmd.
author: rothja 
ms.author: jroth 
manager: jhubbard
ms.date: 10/02/2017
ms.topic: article
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: sql-linux
ms.suite: "sql"
ms.custom: ""
ms.technology: database-engine
ms.assetid: 31ddfb80-f75c-4f51-8540-de6213cb68b8
ms.workload: "On Demand"
---
# Install SQL Server and create a database on SUSE Linux Enterprise Server

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

In this quickstart, you first install SQL Server 2017 on SUSE Linux Enterprise Server (SLES) v12 SP2. Then connect with **sqlcmd** to create your first database and run queries.

> [!TIP]
> This tutorial requires user input and an internet connection. If you are interested in the [unattended](sql-server-linux-setup.md#unattended) or [offline](sql-server-linux-setup.md#offline) installation procedures, see [Installation guidance for SQL Server on Linux](sql-server-linux-setup.md).

## Prerequisites

You must have a SLES v12 SP2 machine with **at least 2 GB** of memory. The file system must be **XFS** or **EXT4**. Other file systems, such as **BTRFS**, are unsupported.

To install SUSE Linux Enterprise Server on your own machine, go to [https://www.suse.com/products/server](https://www.suse.com/products/server). You can also create SLES virtual machines in Azure. See [Create and Manage Linux VMs with the Azure CLI](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-manage-vm), and use `--image SLES` in the call to `az vm create`.

> [!NOTE]
> At this time, the [Windows Subsystem for Linux](https://msdn.microsoft.com/commandline/wsl/about) for Windows 10 is not supported as an installation target.

For other system requirements, see [System requirements for SQL Server on Linux](sql-server-linux-setup.md#system).

## <a id="install"></a>Install SQL Server

To configure SQL Server on SLES, run the following commands in a terminal to install the **mssql-server** package:

> [!IMPORTANT]
> If you have previously installed a CTP or RC release of SQL Server 2017, you must first remove the old repository before registering one of the GA repositories. For more information, see [Change repositories from the preview repository to the GA repository](sql-server-linux-change-repo.md).

1. Download the Microsoft SQL Server SLES repository configuration file:

   ```bash
   sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/mssql-server-2017.repo
   sudo zypper --gpg-auto-import-keys refresh
   ```

   > [!NOTE]
   > This is the Cumulative Update (CU) repository. For more information about your repository options and their differences, see [Change source repositories](sql-server-linux-setup.md#repositories).

1. Run the following commands to install SQL Server:

   ```bash
   sudo zypper install -y mssql-server
   ```

1. After the package installation finishes, run **mssql-conf setup** and follow the prompts to set the SA password and choose your edition.

   ```bash
   sudo /opt/mssql/bin/mssql-conf setup
   ```

   > [!TIP]
   > If you are trying SQL Server 2017 in this tutorial, the following editions are freely licensed: Evaluation, Developer, and Express.

   > [!NOTE]
   > Make sure to specify a strong password for the SA account (Minimum length 8 characters, including uppercase and lowercase letters, base 10 digits and/or non-alphanumeric symbols).

1. Once the configuration is done, verify that the service is running:

   ```bash
   systemctl status mssql-server
   ```

1. If you plan to connect remotely, you might also need to open the SQL Server TCP port (default 1433) on your firewall. If you are using the SuSE firewall, you need to edit the **/etc/sysconfig/SuSEfirewall2** configuration file. Modify the **FW_SERVICES_EXT_TCP** entry to include the SQL Server port number.

   ```
   FW_SERVICES_EXT_TCP="1433"
   ```

At this point, SQL Server is running on your SLES machine and is ready to use!

## <a id="tools"></a>Install the SQL Server command-line tools

To create a database, you need to connect with a tool that can run Transact-SQL statements on the SQL Server. The following steps install the SQL Server command-line tools: [sqlcmd](../tools/sqlcmd-utility.md) and [bcp](../tools/bcp-utility.md).

1. Add the Microsoft SQL Server repository to Zypper.

   ```bash
   sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/prod.repo 
   sudo zypper --gpg-auto-import-keys refresh
   ```

1. Install **mssql-tools** with the unixODBC developer package.

   ```bash
   sudo zypper install -y mssql-tools unixODBC-devel
   ```

1. For convenience, add `/opt/mssql-tools/bin/` to your **PATH** environment variable. This enables you to run the tools without specifying the full path. Run the following commands to modify the **PATH** for both login sessions and interactive/non-login sessions:

   ```bash
   echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
   echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
   source ~/.bashrc
   ```

> [!TIP]
> **Sqlcmd** is just one tool for connecting to SQL Server to run queries and perform management and development tasks. Other tools include:
>
> * [SQL Server Operations Studio (Preview)](../sql-operations-studio/what-is.md)
> * [SQL Server Management Studio](sql-server-linux-develop-use-ssms.md)
> * [Visual Studio Code](sql-server-linux-develop-use-vscode.md).
> * [mssql-cli (Preview)](https://blogs.technet.microsoft.com/dataplatforminsider/2017/12/12/try-mssql-cli-a-new-interactive-command-line-tool-for-sql-server/)

[!INCLUDE [Connect, create, and query data](../includes/sql-linux-quickstart-connect-query.md)]
