---
title: Configure SQL Server settings with environment variables | Microsoft Docs
description: This topic describes how to use environment variables to configure specific SQL Server 2017 settings on Linux.
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 07/21/2017
ms.topic: article
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: sql-linux
ms.suite: "sql"
ms.custom: ""
ms.technology: database-engine
ms.assetid: 
ms.workload: "On Demand"
---
# Configure SQL Server settings with environment variables on Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

You can use several different environment variables to configure SQL Server 2017 on Linux. These variables are used in two scenarios:

- To configure initial setup with the `mssql-conf setup` command.
- To configure a new [SQL Server container in Docker](quickstart-install-connect-docker.md).

> [!TIP]
> If you need to configure SQL Server after these setup scenarios, see [Configure SQL Server on Linux with the mssql-conf tool](sql-server-linux-configure-mssql-conf.md).

## Environment variables

| Environment variable | Description |
|-----|-----|
| **ACCEPT_EULA** | Accept the SQL Server license agreement when set to any value (for example, 'Y'). |
| **MSSQL_SA_PASSWORD** | Configure the SA user password. |
| **MSSQL_PID** | Set the SQL Server edition or product key. Possible values include: </br></br>**Evaluation**</br>**Developer**</br>**Express**</br>**Web**</br>**Standard**</br>**Enterprise**</br>**A product key**</br></br>If specifying a product key, it must be in the form of #####-#####-#####-#####-#####, where '#' is a number or a letter.|
| **MSSQL_LCID** | Sets the language ID to use for SQL Server. For example 1036 is French. |
| **MSSQL_COLLATION** | Sets the default collation for SQL Server. This overrides the default mapping of language id (LCID) to collation. |
| **MSSQL_MEMORY_LIMIT_MB** | Sets the maximum amount of memory (in MB) that SQL Server can use. By default it is 80% of the total physical memory. |
| **MSSQL_TCP_PORT** | Configure the TCP port that SQL Server listens on (default 1433). |
| **MSSQL_IP_ADDRESS** | Set the IP address. Currently, the IP address must be IPv4 style (0.0.0.0). |
| **MSSQL_BACKUP_DIR** | Set the Default backup directory location. |
| **MSSQL_DATA_DIR** | Change the directory where the new SQL Server database data files (.mdf) are created. |
| **MSSQL_LOG_DIR** | Change the directory where the new SQL Server database log (.ldf) files are created. |
| **MSSQL_DUMP_DIR** | Change the directory where SQL Server will deposit the memory dumps and other troubleshooting files by default. |
| **MSSQL_ENABLE_HADR** | Enable Availability Groups. |

## Example: initial setup

This example runs `mssql-conf setup` with configured environment variables. The following environment variables are specified:

- **ACCEPT_EULA** accepts the end user license agreement.
- **MSSSQL_PID** specifies the freely licensed Developer Edition of SQL Server for non-production use.
- **MSSQL_SA_PASSWORD** sets a strong password.
- **MSSQL_TCP_PORT** sets the TCP port that SQL Server listens on to 1234.

```bash
sudo ACCEPT_EULA='Y' MSSQL_PID='Developer' MSSQL_SA_PASSWORD='<YourStrong!Passw0rd>' MSSQL_TCP_PORT=1234 /opt/mssql/bin/mssql-conf setup
```

## Example: Docker

This example docker command uses the following environment variables to create a new SQL Server 2017 container:

- **ACCEPT_EULA** accepts the end user license agreement.
- **MSSSQL_PID** specifies the freely licensed Developer Edition of SQL Server for non-production use.
- **MSSQL_SA_PASSWORD** sets a strong password.
- **MSSQL_TCP_PORT** sets the TCP port that SQL Server listens on to 1234. This means that instead of mapping port 1433 (default) to a host port, the custom TCP port must be mapped with the `-p 1234:1234` command in this example.

If you are running Docker on Linux/macOS, use the following syntax with single quotes:

```bash
docker run -e ACCEPT_EULA=Y -e MSSQL_PID='Developer' -e MSSQL_SA_PASSWORD='<YourStrong!Passw0rd>' -e MSSQL_TCP_PORT=1234 -p 1234:1234 -d microsoft/mssql-server-linux:2017-latest
```

If you are running Docker on Windows, use the following syntax with double quotes:

```bash
docker run -e ACCEPT_EULA=Y -e MSSQL_PID="Developer" -e MSSQL_SA_PASSWORD="<YourStrong!Passw0rd>" -e MSSQL_TCP_PORT=1234 -p 1234:1234 -d microsoft/mssql-server-linux:2017-latest
```

> [!NOTE]
> The process for running production editions in containers is slightly different. For more information, see [Run production container images](sql-server-linux-configure-docker.md#production).

## Next steps

For other SQL Server settings not listed here, see [Configure SQL Server on Linux with the mssql-conf tool](sql-server-linux-configure-mssql-conf.md).

For more information on how to install and run SQL Server on Linux, see [Install SQL Server on Linux](sql-server-linux-setup.md).
