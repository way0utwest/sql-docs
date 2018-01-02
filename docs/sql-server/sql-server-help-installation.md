---
title: SQL Server help content and Help Viewer | Microsoft Docs
ms.custom: ""
ms.date: "12/15/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-non-specified"
ms.service: ""
ms.component: "sql-non-specified"
ms.technology: "server-general"
ms.reviewer: ""
ms.suite: "sql"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "SQL Server 2014"
  - "SQL Server 2016"
  - "SQL Server 2017"
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
caps.latest.revision: 8
author: "craigg-msft"
ms.author: "craigg"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQL Server offline help and Help Viewer

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

You can use the Help Viewer in SQL Server Management Studio (SSMS) or Visual Studio (VS) to download and install SQL Server help packages from online sources or disk and view them offline. This article describes tools that install the Help Viewer, how to install offline help content, and how to view help for [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)], SQL Server 2016, and SQL Server 2017.

> [!NOTE]
> SQL Server 2016 and SQL Server 2017 help are combined, although some topics apply to individual versions where noted. Most topics apply to both.

## Install the Help Viewer

The Help Viewer has two versions: v2.x supports SQL Server 2016/SQL Server 2017 help, and v1.x supports [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] help. The Help Viewer does not support proxy settings, and does not support the ISO format. 

The following tools install the Help Viewer: 

|**Tool that installs Help Viewer**|**Help Viewer version installed**|
|---------|---------|
|[SQL Server Management Studio 17.x](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)| v2.2|
|[SQL Server Data Tools for Visual Studio 2015](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt)| v2.2|
|Visual Studio 2017* | v2.3|
|Visual Studio 2015 | v2.2|
|SQL Server 2014 Management Studio | v1.x|
|Earlier versions of Visual Studio | v1.x|
|SQL Server 2016 | v1.x|

\* To install the Help Viewer with Visual Studio 2017, on the Individual Components tab in the Visual Studio Installer, select **Help Viewer** under Code Tools, and then click **Install**. 

>[!NOTE]
> - SQL Server 2016 installs Help Viewer 1.1, which does not support SQL Server 2016 help. 
> - Installing SQL Server 2017 does not install any Help Viewer.
> - Help Viewer v2.x can also support [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] help, if you install the content from disk.

## Use Help Viewer v2.x

SSMS 17.x and VS 2015 and 2017 use Help Viewer 2.x, which supports SQL Server 2016/2017 Help. 

**To download and install offline help content with Help Viewer v2.x**

1. In SSMS or VS, click **Add and Remove Help Content** on the Help menu. 

   ![HelpViewer2 Add Remove Content](../sql-server/media/sql-server-help-installation/addremovecontent.png)  

   The Help Viewer opens to the Manage Content tab.  
   
2. To install the latest help content package, choose **Online** under Installation source.
   
   ![HelpViewer2_ManageContent_OnlineSource](../sql-server/media/sql-server-help-installation/helpviewer2-managecontent-onlinesource.png)  
   
   >[!NOTE]
   > To install from disk (SQL Server 2014 help), choose **Disk** under Installation source, and specify the disk location.
   
   The Local store path on the Manage Content tab shows where the content will be installed on the local computer. If you want to change the location, click **Move**, enter a different folder path in the **To** field, and then click **OK**.
   If the help installation fails after changing the Local store path, close and reopen the Help Viewer, ensure the new location appears in the Local store path, and then try the installation again.

3. Click **Add** next to each content package (book) that you want to install. 
   To install all SQL Server help content, add all 13 books under SQL Server. 
   
4. Click **Update** at lower right. 
   The help table of contents on the left automatically updates with the added books. 
   
   ![HelpViewer2_ManageContent_AddContent](../sql-server/media/sql-server-help-installation/helpviewer2-managecontent-addcontent.png)     
   
> [!NOTE]
> Not all the top-node titles in the SQL Server table of contents exactly match the names of the corresponding downloadable help books. The TOC titles map to the book names as follows:

| Contents pane | SQL Server book |
|-----|-----|
|Analysis services language reference | Analysis Services (MDX) language reference|
|Data Analysis Expressions (DAX) reference | Data Analysis Expressions (DAX) reference|
|Data mining extensions (DMX) reference | Data mining extensions (DMX) reference|
|Developer Guides for SQL Server | SQL Server Developer Reference|
|Download SQL Server Management Studio | SQL Server Management Studio|
|Getting started with machine learning in SQL Server | Microsoft Machine Learning Services|
|Power Query M Reference | Power Query M Reference|
|SQL Server Drivers | SQL Server Connection Drivers|
|SQL Server on Linux | SQL Server on Linux|
|SQL Server Technical Documentation | SQL Server Technical Documentation (SSIS, SSRS, DB engine, setup)|
|Tools and utilities for Azure SQL Database | SQL Server tools|
|Transact-SQL Reference (Database Engine) | Transact-SQL Reference|
|XQuery Language Reference (SQL Server) | XQuery Language Reference (SQL Server)|

> [!NOTE]
> If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future. For more information about this issue, see [Visual Studio Help Viewer freezes](https://msdn.microsoft.com/en-us/library/dd831853.aspx).

**To view offline help content in SSMS with Help Viewer v2.x**

To view the installed help in SSMS, press CTRL + ALT + F1, or choose **Add or Remove Content** from the Help menu, to launch the Help Viewer. 

   ![HelpViewer2 Add Remove Content](../sql-server/media/sql-server-help-installation/addremovecontent.png)  

The Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane. Click topics in the table of contents to display them in the right pane. 
> [!TIP]
> If the contents pane is not visible, click Contents on the left margin. Click the pushpin icon to keep the contents pane open.  

   ![Help Viewer v2.x with content](../sql-server/media/sql-server-help-installation/helpviewer2-withcontentinstalled.png)

**To view offline help content in VS with Help Viewer v2.x**

To view the installed help in Visual Studio:
1. Point to **Set Help Preference** on the Help menu and choose **Launch in Help Viewer**. 

   ![VS Help View Set Preference Help Viewer](../sql-server/media/sql-server-help-installation/launchviewer.png)

2. Click **View Help** in the Help menu to display the content in the Help Viewer. 

   ![View Help](../sql-server/media/sql-server-help-installation/viewhelp.png)

   The help table of contents shows on the left, and the selected help topic on the right. 
   
## Use Help Viewer v1.x

Earlier versions of SSMS and VS use Help Viewer 1.x, which supports SQL Server 2014 Help. 

**To download and install offline help content with Help Viewer v1.x**

This process uses Help Viewer 1.x to download SQL Server 2014 help from the Microsoft Download Center and install it on your computer.

1. Navigate to the [Product Documentation for Microsoft SQL Server 2014](https://www.microsoft.com/en-us/download/details.aspx?id=42557) download site and click **Download**.  
2. Click **Save** in the message box to save the *SQLServer2014Documentation\_\*.exe* file to your computer.  
   
   >[!NOTE]
   >For firewall and proxy restricted environments, save the download to a USB drive or other portable media that can be carried into the environment.   
   
3. Double-click the .exe to unpack the help content file, and save the file to a local or shared folder.  
4. Open the **Help Library Manager** by launching SSMS or VS and clicking **Manage Help Settings** on the Help menu.  
5. Click **Install content from disk**, and browse to the folder where you unpacked the help content file.  
   
   ![HelpLibraryManager_MainPage_InstallFromDisk](../sql-server/media/sql-server-help-installation/helplibrarymanager-mainpage-installfromdisk.png)
   
   ![HelpLibraryManager_InstallContentFromDisk_dialog1](../sql-server/media/sql-server-help-installation/helplibrarymanager-installcontentfromdisk-dialog1.png)
   
   > [!IMPORTANT]
   > To avoid installing local help content that has only a partial table of contents, you must use the **Install content from disk** option in the **Help Library Manager**.  If you used **Install content from online** and the Help Viewer is displaying a partial table of contents, see this [blog post](https://blogs.msdn.microsoft.com/womeninanalytics/2016/06/21/troubleshoot-local-help-for-sql-server-2014/) for troubleshooting steps. 
   
8. Click the HelpContentSetup.msha file, click **Open**, and then click **Next**.  
9. Click **Add** next to the documentation you want to install, and then click **Update**.  
   
   ![HelpLibraryManager_InstallContentFromDisk_dialog2](../sql-server/media/sql-server-help-installation/helplibrarymanager-installcontentfromdisk-dialog2.png)  
   
10. Click **Finish**, and then click **Exit**.

**To view offline help content with Help Viewer v1.x**

11. To view installed help, open **Help Library Manager**, click **Choose online or local help**, and then click **I want to use local help**.
12. Open the Help Viewer to see the content by clicking **View Help** on the **Help** menu. The content you installed is listed in the left pane.  
   
   ![HelpViewer1_withContentInstalled_ZoomedIn](../sql-server/media/sql-server-help-installation/helpviewer1-withcontentinstalled-zoomedin.png)  
   
## View online help

Online help always shows the most up-to-date content. 

**To view SQL Server online help in SSMS 17.x**

- Click **View Help** in the **Help** menu. The latest SQL Server 2016/2017 documentation from [https://docs.microsoft.com/sql/https://docs.microsoft.com/en-us/sql/sql-server/sql-server-technical-documentation](https://docs.microsoft.com/en-us/sql/sql-server/sql-server-technical-documentation) displays in a browser. 

   ![View Help](../sql-server/media/sql-server-help-installation/viewhelp.png)

**To view Visual Studio online help in Visual Studio**

1. Point to **Set Help Preference** on the Help menu and choose either **Launch in Browser** or **Launch in Help Viewer**. 
2. Click **View Help** in the Help menu. The latest Visual Studio help displays in the chosen environment. 

**To view online help with Help Viewer v1.x**

1. Open the **Help Library Manager** by clicking **Manage Help Settings** on the Help menu.  
2. In the Help Library Manager dialog box, click **Choose online or local help**.  
   
   ![HelpLibraryManager_MainPage_ChooseOnlineORLocal.png](../sql-server/media/sql-server-help-installation/helplibrarymanager-mainpage-chooseonlineorlocal.png.png)  
   
3. Click **I want to use online help**, click **OK**, and then click **Exit**.  
   
   ![HelpLibraryManager_ChooseOnlineORLocalHelp_OnlineHelpSelected_dialog](../sql-server/media/sql-server-help-installation/helplibrarymanager-chooseonlineorlocalhelp-onlinehelpselected-dialog.png)
   
4. Open the Help Viewer to see the content by clicking **View Help** on the **Help** menu. 

## View F1 help

When you press F1 or click **Help** or the **?** icon in a dialog box in SSMS or VS, a context-sensitive online help topic appears in the browser or Help Viewer. 

**To view F1 help**

1. Point to **Set Help Preference** on the Help menu, and choose either **Launch in Browser** or **Launch in Help Viewer**. 
2. Press F1, or click **Help** or **?** in dialog boxes where they are available, to see context-sensitive online topics in the chosen environment.

>  [!NOTE]
>  F1 help only works when you are online. There are no offline sources for F1 help. 
   

## Next steps
[Microsoft Help Viewer - Visual Studio](/visualstudio/ide/microsoft-help-viewer)  

[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]
