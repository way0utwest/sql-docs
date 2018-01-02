---
title: "Deploy an SSIS project with Transact-SQL (VS Code) | Microsoft Docs"
ms.date: "09/25/2017"
ms.topic: "article"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "quick-start"
ms.suite: "sql"
ms.custom: ""
ms.technology: 
  - "integration-services"
author: "douglaslMS"
ms.author: "douglasl"
manager: "craigg"
ms.workload: "Inactive"
---
# Deploy an SSIS project from Visual Studio Code with Transact-SQL
This quick start demonstrates how to use Visual Studio Code to connect to the SSIS Catalog database, and then use Transact-SQL statements to deploy an SSIS project to the SSIS Catalog.

> [!NOTE]
> The method described in this article is not available when you connect to an Azure SQL Database server with VS Code. The `catalog.deploy_project` stored procedure expects path to the `.ispac` file in the local (on premises) file system.

Visual Studio Code is a code editor for Windows, macOS, and Linux that supports extensions, including the `mssql` extension for connecting to Microsoft SQL Server, Azure SQL Database, or Azure SQL Data Warehouse. For more info about VS Code, see [Visual Studio Code](https://code.visualstudio.com/).

## Prerequisites

Before you start, make sure you have installed the latest version of Visual Studio Code and loaded the `mssql` extension. To download these tools, see the following pages:
-   [Download Visual Studio Code](https://code.visualstudio.com/Download)
-   [mssql extension](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql)

## Set language mode to SQL in VS Code

To enable `mssql` commands and T-SQL IntelliSense, set the language mode to **SQL** in Visual Studio Code.

1. Open Visual Studio Code and then open a new window. 

2. Click **Plain Text** in the lower right-hand corner of the status bar.
 
3. In the **Select language mode** drop-down menu that opens, select or enter **SQL**, and then press **ENTER** to set the language mode to SQL. 

## Connect to the SSIS Catalog database

Use Visual Studio Code to establish a connection to the SSIS Catalog.

> [!IMPORTANT]
> Before continuing, make sure that you have your server, database, and login information ready. If you change your focus from Visual Studio Code after you begin entering the connection profile information, you have to restart creating the connection profile.

1. In VS Code, press **CTRL+SHIFT+P** (or **F1**) to open the Command Palette.

2. Type **sqlcon** and press **ENTER**.

3. Press **ENTER** to select **Create Connection Profile**. This step creates a connection profile for your SQL Server instance.

4. Follow the prompts to specify the connection properties for the new connection profile. After specifying each value, press **ENTER** to continue. 

   | Setting       | Suggested value | More info |
   | ------------ | ------------------ | ------------------------------------------------- | 
   | **Server name** | The fully qualified server name |  |
   | **Database name** | **SSISDB** | The name of the database to which to connect. |
   | **Authentication** | SQL Login| This quickstart uses SQL authentication. |
   | **User name** | The server admin account | This is the account that you specified when you created the server. |
   | **Password (SQL Login)** | The password for your server admin account | This is the password that you specified when you created the server. |
   | **Save Password?** | Yes or No | If you do not want to enter the password each time, select Yes. |
   | **Enter a name for this profile** | A profile name, such as **mySSISServer** | A saved profile name speeds your connection on subsequent logins. | 

5. Press the **ESC** key to close the info message that informs you that the profile is created and connected.

6. Verify your connection in the status bar.

## Run the T-SQL code
Run the following Transact-SQL code to deploy an SSIS project.

1. In the **Editor** window, enter the following query in the empty query window.

2. Update the parameter values in the `catalog.deploy_project` stored procedure for your system.

3. Press **CTRL+SHIFT+E** to run the code and deploy the project.

```sql
DECLARE @ProjectBinary AS varbinary(max)
DECLARE @operation_id AS bigint
SET @ProjectBinary = (SELECT * FROM OPENROWSET(BULK '<project_file_path>.ispac', SINGLE_BLOB) AS BinaryData)

EXEC catalog.deploy_project @folder_name = '<target_folder>',
    @project_name = '<project_name',
    @Project_Stream = @ProjectBinary,
    @operation_id = @operation_id out
```

## Next steps
- Consider other ways to deploy a package.
    - [Deploy an SSIS package with SSMS](./ssis-quickstart-deploy-ssms.md)
    - [Deploy an SSIS package with Transact-SQL (SSMS)](./ssis-quickstart-deploy-tsql-ssms.md)
    - [Deploy an SSIS package from the command prompt](./ssis-quickstart-deploy-cmdline.md)
    - [Deploy an SSIS package with PowerShell](ssis-quickstart-deploy-powershell.md)
    - [Deploy an SSIS package with C#](./ssis-quickstart-deploy-dotnet.md) 
- Run a deployed package. To run a package, you can choose from several tools and languages. For more info, see the following articles:
    - [Run an SSIS package with SSMS](./ssis-quickstart-run-ssms.md)
    - [Run an SSIS package with Transact-SQL (SSMS)](./ssis-quickstart-run-tsql-ssms.md)
    - [Run an SSIS package with Transact-SQL (VS Code)](ssis-quickstart-run-tsql-vscode.md)
    - [Run an SSIS package from the command prompt](./ssis-quickstart-run-cmdline.md)
    - [Run an SSIS package with PowerShell](ssis-quickstart-run-powershell.md)
    - [Run an SSIS package with C#](./ssis-quickstart-run-dotnet.md) 
