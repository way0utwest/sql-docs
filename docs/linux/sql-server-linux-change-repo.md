---
title: Register the the General Availability repository for SQL Server on Linux | Microsoft Docs
description: Change repositories from the preview SQL Server 2017 repository to the General Availability (GA) repository on Linux (GA is also sometimes referred to as RTM).
author: annashres 
ms.author: anshrest 
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
ms.workload: "Inactive"
---
# Change repositories from the preview repository to the GA repository

When you upgrade SQL Server 2017 from CTP 2.1, RC1, or RC2 to the General Availability (GA) release you have to switch repositories. The following sections explain your choice of repositories and how to make the change before upgrading.

## Repository choices

It is important to note that there are two main types of repositories for each distribution:

  > [!IMPORTANT]
  > Any version prior to CTP 2.1 must be upgraded to at least 2.1 before upgrading to GA.

- **Cumulative Updates (CU)**: The Cumulative Update (CU) repository contains packages for the base SQL Server release and any bug fixes or improvements since that release. Cumulative updates are specific to a release version, such as SQL Server 2017. They are released on a regular cadence.

- **GDR**: The GDR repository contains packages for the base SQL Server release and only critical fixes and security updates since that release. These updates are also added to the next CU release.

Each CU and GDR release contains the full SQL Server package and all previous updates for that repository. Updating from a GDR release to a CU release is supported by changing your configured repository for SQL Server. You can also [downgrade](sql-server-linux-setup.md#rollback) to any release within your major version (ex: 2017).

> [!NOTE]
> You can update from a GDR release to CU release at any time by changing repositories. Updating from a CU release to a GDR release is not supported. 

## Change to a GA repository

To change from the preview repository to one source repository (CU or GDR), use the following steps:

1. Remove the previously configured preview repository.

   | Platform | Repository removal command |
   |-----|-----|
   | RHEL | `sudo rm -rf /etc/yum.repos.d/mssql-server.repo` |
   | SLES | `sudo zypper removerepo 'packages-microsoft-com-mssql-server'` |
   | Ubuntu | `sudo add-apt-repository -r 'deb [arch=amd64] https://packages.microsoft.com/ubuntu/16.04/mssql-server xenial main'` |

1. For **Ubuntu only**, import the public repository GPG keys.

   ```bash
   sudo curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
   ```

1. Configure the new repository.

   | Platform | Repository | Command |
   |-----|-----|-----|
   | RHEL | CU | `sudo curl -o /etc/yum.repos.d/mssql-server.repo https://packages.microsoft.com/config/rhel/7/mssql-server-2017.repo` |
   | RHEL | GDR | `sudo curl -o /etc/yum.repos.d/mssql-server.repo https://packages.microsoft.com/config/rhel/7/mssql-server-2017-gdr.repo` |
   | SLES | CU  | `sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/mssql-server-2017.repo` |
   | SLES | GDR | `sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/mssql-server-2017-gdr.repo` |
   | Ubuntu | CU | `sudo add-apt-repository "$(curl https://packages.microsoft.com/config/ubuntu/16.04/mssql-server-2017.list)" && sudo apt-get update` |
   | Ubuntu | GDR | `sudo add-apt-repository "$(curl https://packages.microsoft.com/config/ubuntu/16.04/mssql-server-2017-gdr.list)" && sudo apt-get update` |

1. [Install](sql-server-linux-setup.md#platforms) or [update](sql-server-linux-setup.md#upgrade) SQL Server using the GA repository.

   > [!IMPORTANT]
   > At this point, if you choose to perform a full installation using the [quickstart tutorials](#platforms), remember that you have just configured the target repository. Do not repeat that step in the tutorials. This is especially true if you configure the GDR repository, because the quickstart tutorials use the CU repository.

## Next steps

For more information on how to install SQL Server 2017 on Linux, see [Installation guidance for SQL Server on Linux](sql-server-linux-setup.md).
