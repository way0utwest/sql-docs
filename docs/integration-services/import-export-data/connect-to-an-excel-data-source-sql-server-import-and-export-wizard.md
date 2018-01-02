---
title: "Connect to an Excel Data Source (SQL Server Import and Export Wizard) | Microsoft Docs"
ms.custom: ""
ms.date: "06/20/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "import-export-data"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43fbaca0-36d8-4583-9056-af7010209b87
caps.latest.revision: 12
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Connect to an Excel Data Source (SQL Server Import and Export Wizard)
This topic shows you how to connect to a **Microsoft Excel** data source from the **Choose a Data Source** or **Choose a Destination** page of the SQL Server Import and Export Wizard.

The following screen shot shows a sample connection to a Microsoft Excel workbook.

![Excel connection](../../integration-services/import-export-data/media/excel-connection.png) 

## Options to specify

> [!NOTE]
> The connection options for this data provider are the same whether Excel is your source or your destination. That is, the options you see are the same on both the **Choose a Data Source** and the **Choose a Destination** pages of the wizard.

**Excel file path**  
 Specify the path and file name for the Excel file. For example:
-   For a file on the local computer, **C:\\MyData.xlsx**.
-   For a file on a network share, **\\\\Sales\\Database\\Northwind.xlsx**.

Or, click **Browse**.  
  
 **Browse**  
 Locate the spreadsheet by using the **Open** dialog box.  

> [!NOTE]
> The wizard can't open a password-protected Excel file.

 **Excel version**  
Select the version of Excel that's used by the source workbook.

> [!IMPORTANT]
> You may have to download and install additional files to connect to Excel files. See [Get the files you need to connect to Excel](#officeDownloads) on this page for more info.

**First row has column names**  
Indicate whether the first row of the data contains column names.
-   If the data doesn't contain column names but you enable this option, the wizard treats the first row of source data as the column names.
-   If the data contains column names but you disable this option, the wizard treats the row of column names as the first row of data.

If you specify that the data doesn't have column names, the wizard uses F1, F2, and so forth, as column headings.

## I don't see Excel in the list of data sources
If you don't see Excel in the list of data sources, are you running the 64-bit wizard? The providers for Excel and Access are typically 32-bit and aren't visible in the 64-bit wizard. Run the 32-bit wizard instead.

> [!NOTE]
> To use the 64-bit version of the SQL Server Import and Export Wizard, you have to install SQL Server. SQL Server Data Tools (SSDT) and SQL Server Management Studio (SSMS) are 32-bit applications and only install 32-bit files, including the 32-bit version of the wizard.

## <a name="officeDownloads"></a>Get the files you need to connect to Excel  
You may have to download the connectivity components for Microsoft Office data sources, including Excel and Access, if they're not already installed. Download the latest version of the connectivity components for both Excel and Access files here:
[Microsoft Access Database Engine 2016 Redistributable](https://www.microsoft.com/download/details.aspx?id=54920).
  
The latest version of the components can open files created by earlier versions of Excel.

If the computer has a 32-bit version of Office, then you have to install the 32-bit version of the components, and you also have to ensure that you run the package in 32-bit mode.

If you have an Office 365 subscription, make sure that you download the Access Database Engine 2016 Redistributable and not the Microsoft Access 2016 Runtime. When you run the installer, you may see an error message that you can't install the download side-by-side with Office click-to-run components. To bypass this error message, run the installation in quiet mode by opening a Command Prompt window and running the .EXE file that you downloaded with the `/quiet` switch. For example:

`C:\Users\<user name>\Downloads\AccessDatabaseEngine.exe /quiet`

## See also
[Choose a Data Source](../../integration-services/import-export-data/choose-a-data-source-sql-server-import-and-export-wizard.md)  
[Choose a Destination](../../integration-services/import-export-data/choose-a-destination-sql-server-import-and-export-wizard.md)

