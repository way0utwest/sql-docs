---
title: Install SQL Server 2017 on Linux | Microsoft Docs
description: Install, update, and uninstall SQL Server on Linux. This topic covers online, offline, and unattended scenarios. 
author: rothja 
ms.author: jroth 
manager: jhubbard
ms.date: 12/21/2017
ms.topic: article
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: sql-linux
ms.suite: "sql"
ms.custom: ""
ms.technology: database-engine
ms.assetid: 565156c3-7256-4e63-aaf0-884522ef2a52
ms.workload: "Active"
---
# Installation guidance for SQL Server on Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

This topic explains how to install, update, and uninstall SQL Server 2017 on Linux. SQL Server 2017 is supported on Red Hat Enterprise Linux (RHEL), SUSE Linux Enterprise Server (SLES), and Ubuntu. It is also available as a Docker image, which can run on Docker Engine on Linux or Docker for Windows/Mac.

> [!TIP]
> To get started quickly, jump to one of the quickstarts for [RHEL](quickstart-install-connect-red-hat.md), [SLES](quickstart-install-connect-suse.md), [Ubuntu](quickstart-install-connect-ubuntu.md), or [Docker](quickstart-install-connect-docker.md).

## <a id="supportedplatforms"></a> Supported platforms

SQL Server 2017 is supported on the following Linux platforms:

| Platform | Supported version(s) | Get
|-----|-----|-----
| **Red Hat Enterprise Linux** | 7.3 or 7.4 | [Get RHEL 7.4](http://access.redhat.com/products/red-hat-enterprise-linux/evaluation)
| **SUSE Linux Enterprise Server** | v12 SP2 | [Get SLES v12 SP2](https://www.suse.com/products/server)
| **Ubuntu** | 16.04 | [Get Ubuntu 16.04](http://www.ubuntu.com/download/server)
| **Docker Engine** | 1.8+ | [Get Docker](http://www.docker.com/products/overview)

Microsoft supports deploying and managing SQL Server containers by using OpenShift and Kubernetes.

For the latest support policy for SQL Server 2017, see [Technical support policy for Microsoft SQL Server](https://support.microsoft.com/help/4047326/support-policy-for-microsoft-sql-server).

## <a id="system"></a> System requirements

SQL Server 2017 has the following system requirements for Linux:

|||
|-----|-----|
| **Memory** | 2 GB |
| **File System** | **XFS** or **EXT4** (other file systems, such as **BTRFS**, are unsupported) |
| **Disk space** | 6 GB |
| **Processor speed** | 2 GHz |
| **Processor cores** | 2 cores |
| **Processor type** | x64-compatible only |

If you use **Network File System (NFS)** remote shares in production, note the following support requirements:

- Use NFS version **4.2 or higher**. Older versions of NFS do not support required features, such as fallocate and sparse file creation, common to modern file systems.
- Locate only the **/var/opt/mssql** directories on the NFS mount. Other files, such as the SQL Server system binaries, are not supported.
- Ensure that NFS clients use the 'nolock' option when mounting the remote share.

## <a id="platforms"></a> Install SQL Server

You can install SQL Server on Linux from the command line. For instructions, see one of the following quickstarts:

- [Install on Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Install on SUSE Linux Enterprise Server](quickstart-install-connect-suse.md)
- [Install on Ubuntu](quickstart-install-connect-ubuntu.md)
- [Run on Docker](quickstart-install-connect-docker.md)
- [Provision a SQL VM in Azure](/azure/virtual-machines/linux/sql/provision-sql-server-linux-virtual-machine?toc=%2fsql%2flinux%2ftoc.json)

## <a id="upgrade"></a> Update SQL Server

To update the **mssql-server** package to the latest release, use one of the following commands based on your platform:

| Platform | Package update command(s) |
|-----|-----|
| RHEL | `sudo yum update mssql-server` |
| SLES | `sudo zypper update mssql-server` |
| Ubuntu | `sudo apt-get update`<br/>`sudo apt-get install mssql-server` |

These commands download the newest package and replace the binaries located under `/opt/mssql/`. The user generated databases and system databases are not affected by this operation.

## <a id="rollback"></a> Rollback SQL Server

To rollback or downgrade SQL Server to a previous release, use the following steps:

1. Identify the version number for the SQL Server package you want to downgrade to. For a list of package numbers, see the [Release notes](sql-server-linux-release-notes.md).

1. Downgrade to a previous version of SQL Server. In the following commands, replace `<version_number>` with the SQL Server version number you identified in step one.

   | Platform | Package update command(s) |
   |-----|-----|
   | RHEL | `sudo yum downgrade mssql-server-<version_number>.x86_64` |
   | SLES | `sudo zypper install --oldpackage mssql-server=<version_number>` |
   | Ubuntu | `sudo apt-get install mssql-server=<version_number>`<br/>`sudo systemctl start mssql-server` |

> [!NOTE]
> It is only supported to downgrade to a release within the same major version, such as SQL Server 2017.

## <a id="versioncheck"></a> Check installed SQL Server version

To verify your current version and edition of SQL Server on Linux, use the following procedure:

1. If not already installed, install the [SQL Server command-line tools](sql-server-linux-setup-tools.md).

1. Use **sqlcmd** to run a Transact-SQL command that displays your SQL Server version and edition.

   ```bash
   sqlcmd -S localhost -U SA -Q 'select @@VERSION'
   ```

## <a id="uninstall"></a> Uninstall SQL Server

To remove the **mssql-server** package on Linux, use one of the following commands based on your platform:

| Platform | Package removal command(s) |
|-----|-----|
| RHEL | `sudo yum remove mssql-server` |
| SLES | `sudo zypper remove mssql-server` |
| Ubuntu | `sudo apt-get remove mssql-server` |

Removing the package does not delete the generated database files. If you want to delete the database files, use the following command:

```bash
sudo rm -rf /var/opt/mssql/
```

## <a id="repositories"></a> Configure source repositories

When you install or upgrade SQL Server, you get the latest version of SQL Server from your configured Microsoft repository.

### Repository options

There are two main types of repositories for each distribution:

- **Cumulative Updates (CU)**: The Cumulative Update (CU) repository contains packages for the base SQL Server release and any bug fixes or improvements since that release. Cumulative updates are specific to a release version, such as SQL Server 2017. They are released on a regular cadence.

- **GDR**: The GDR repository contains packages for the base SQL Server release and only critical fixes and security updates since that release. These updates are also added to the next CU release.

Each CU and GDR release contains the full SQL Server package and all previous updates for that repository. Updating from a GDR release to a CU release is supported by changing your configured repository for SQL Server. You can also [downgrade](#rollback) to any release within your major version (ex: 2017). Updating from a CU release to a GDR release is not supported.

### Check your configured repository

If you want to verify what repository is configured, use the following platform-dependent techniques.

| Platform | Procedure |
|-----|-----|
| RHEL | 1. View the files in the **/etc/yum.repos.d** directory: `sudo ls /etc/yum.repos.d`<br/>2. Look for a file that configures the SQL Server directory, such as **mssql-server.repo**.<br/>3. Print out the contents of the file: `sudo cat /etc/yum.repos.d/mssql-server.repo`<br/>4. The **name** property is the configured repository.|
| SLES | 1. Run the following command: `sudo zypper info mssql-server`<br/>2. The **Repository** property is the configured repository. |
| Ubuntu | 1. Run the following command: `sudo cat /etc/apt/sources.list`<br/>2. Examine the package URL for mssql-server. |

The end of the repository URL confirms the repository type:

- **mssql-server**: preview repository.
- **mssql-server-2017**: CU repository.
- **mssql-server-2017-gdr**: GDR repository.

### Change the source repository

To configure the CU or GDR repositories, use the following steps:

> [!NOTE]
> The [quickstarts](#platforms) configure the CU repository. If you follow those tutorials, you do not need to use the steps below to continue using the CU repository. These steps are only necessary for changing your configured repository.

1. If necessary, remove the previously configured repository.

   | Platform | Repository | Repository removal command |
   |---|---|---|
   | RHEL | **All** | `sudo rm -rf /etc/yum.repos.d/mssql-server.repo` |
   | SLES | **CTP** | `sudo zypper removerepo 'packages-microsoft-com-mssql-server'` |
   | | **CU** | `sudo zypper removerepo 'packages-microsoft-com-mssql-server-2017'` |
   | | **GDR** | `sudo zypper removerepo 'packages-microsoft-com-mssql-server-2017-gdr'`|
   | Ubuntu | **CTP** | `sudo add-apt-repository -r 'deb [arch=amd64] https://packages.microsoft.com/ubuntu/16.04/mssql-server xenial main'` 
   | | **CU** | `sudo add-apt-repository -r 'deb [arch=amd64] https://packages.microsoft.com/ubuntu/16.04/mssql-server-2017 xenial main'` | 
   | | **GDR** | `sudo add-apt-repository -r 'deb [arch=amd64] https://packages.microsoft.com/ubuntu/16.04/mssql-server-2017-gdr xenial main'` |

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

1. [Install](#platforms) or [update](#upgrade) SQL Server and any related packages from the new repository.

   > [!IMPORTANT]
   > At this point, if you choose to use one of the installation tutorials, such as the [quickstart tutorials](#platforms), remember that you have just configured the target repository. Do not repeat that step in the tutorials. This is especially true if you configure the GDR repository, because the quickstart tutorials use the CU repository.

## <a id="unattended"></a> Unattended install

You can perform an unattended installation in the following way:

- Follow the initial steps in the [quickstarts](#platforms) to register the repositories and install SQL Server.
- When you run `mssql-conf setup`, set [environment variables](sql-server-linux-configure-environment-variables.md) and use the `-n` (no prompt) option.

The following example configures the Developer edition of SQL Server with the **MSSQL_PID** environment variable. It also accepts the EULA (**ACCEPT_EULA**) and sets the SA user password (**MSSQL_SA_PASSWORD**). The `-n` parameter performs an unprompted installation where the configuration values are pulled from the environment variables.

```bash
sudo MSSQL_PID=Developer ACCEPT_EULA=Y MSSQL_SA_PASSWORD='<YourStrong!Passw0rd>' /opt/mssql/bin/mssql-conf -n setup
```

You can also create a script that performs other actions. For example, you could install other SQL Server packages.

For a more detailed sample script, see the following examples:

- [Red Hat unattended installation script](sample-unattended-install-redhat.md)
- [SUSE unattended installation script](sample-unattended-install-suse.md)
- [Ubuntu unattended installation script](sample-unattended-install-ubuntu.md)

## <a id="offline"></a> Offline install

If your Linux machine does not have access to the online repositories used in the [quick starts](#platforms), you can download the package files directly. These packages are located in the Microsoft repository, [https://packages.microsoft.com](https://packages.microsoft.com).

> [!TIP]
> If you successfully installed with the steps in the quick starts, you do not need to download or manually install the package(s) below. This section is only for the offline scenario.

1. **Download the database engine package for your platform**. Find package download links in the package details section of the [Release Notes](sql-server-linux-release-notes.md).

1. **Move the downloaded package to your Linux machine**. If you used a different machine to download the packages, one way to move the packages to your Linux machine is with the **scp** command.

1. **Install the database engine package**. Use one of the following commands based on your platform. Replace the package file name in this example with the exact name you downloaded.

   | Platform | Package removal command |
   |-----|-----|
   | RHEL | `sudo yum localinstall mssql-server_versionnumber.x86_64.rpm` |
   | SLES | `sudo zypper install mssql-server_versionnumber.x86_64.rpm` |
   | Ubuntu | `sudo dpkg -i mssql-server_versionnumber_amd64.deb` |

    > [!NOTE]
    > You can also install the RPM packages (RHEL and SLES) with the `rpm -ivh` command, but the commands in the previous table automatically install dependencies if available from approved repositories.

1. **Resolve missing dependencies**: You might have missing dependencies at this point. If not, you can skip this step. On Ubuntu, if you have access to approved repositories containing those dependencies, the easiest solution is to use the `apt-get -f install` command. This command also completes the installation of SQL Server. To manually inspect dependencies, use the following commands:

   | Platform | List dependencies command |
   |-----|-----|
   | RHEL | `rpm -qpR mssql-server_versionnumber.x86_64.rpm` |
   | SLES | `rpm -qpR mssql-server_versionnumber.x86_64.rpm` |
   | Ubuntu | `dpkg -I mssql-server_versionnumber_amd64.deb` |

   After resolving the missing dependencies, attempt to install the mssql-server package again.

1. **Complete the SQL Server setup**. Use **mssql-conf** to complete the SQL Server setup:

   ```bash
   sudo /opt/mssql/bin/mssql-conf setup
   ```

## Next steps

After installation, you can also install other optional SQL Server packages.

- [SQL Server command-line tools](sql-server-linux-setup-tools.md)
- [SQL Server Agent](sql-server-linux-setup-sql-agent.md)
- [SQL Server Full Text Search](sql-server-linux-setup-full-text-search.md)
- [SQL Server Integration Services (Ubuntu)](sql-server-linux-setup-ssis.md)

Connect to your SQL Server instance to begin creating and managing databases. To get started, see the quickstarts:

- [Install on Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Install on SUSE Linux Enterprise Server](quickstart-install-connect-suse.md)
- [Install on Ubuntu](quickstart-install-connect-ubuntu.md)
- [Run on Docker](quickstart-install-connect-ubuntu.md)
