---
title: "Add a Custom Report to Management Studio | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-objects"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SQL Server Management Studio [SQL Server], custom reports"
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
caps.latest.revision: 6
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Add a Custom Report to Management Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion_md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] as a custom report. [!INCLUDE[ssRS](../../includes/ssrs_md.md)] can create a wide variety of sophisticated reports. To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull_md.md)] installed on the computer. You do not have to install [!INCLUDE[ssRS](../../includes/ssrs_md.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)].  
  
 
### To create a simple report saved as an .rdl file  
  
1.  Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.  
  
2.  On the **File** menu, point to **New**, and then click **Project**.  
  
3.  In the **Project Types** list, click **Business Intelligence Projects**.  
  
4.  In the **Templates** list, click **Report Server Project Wizard**.  
  
5.  In **Name**, type **ConnectionsReport**, and then click **OK**.  
  
6.  On the **Report Wizard** introduction page, click **Next**.  
  
7.  On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde_md.md)], and then click **Edit**.  
  
8.  In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
9. In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject_md.md)], and then click **OK**.  
  
10. On the **Select the Data Source** page, click **Next**.  
  
11. On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql_md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde_md.md)], and then click **Next**. The Report Wizard Query string box will not accept report parameters. More complex custom reports must be created manually.  
  
    **SELECT session_id, net_transport FROM sys.dm_exec_connections;**  
  
12. On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.  
  
13. On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.  
  
14. Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio_md.md)].  
  
15. Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.  
  
### To add a report to Management Studio  
  
-   In [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**. In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.  
  
    When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node. When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**. If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.  
  
    1.  To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.  
  
    2.  Adjust the number for **Display files in recently used list**.  
  
## See Also  
[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md)  
[Use Custom Reports with Object Explorer Node Properties](../../ssms/object/use-custom-reports-with-object-explorer-node-properties.md)  
[Unsuppress Run Custom Report Warnings](../../ssms/object/unsuppress-run-custom-report-warnings.md)  
[SQL Server Reporting Services](http://msdn.microsoft.com/en-us/b8d18d3d-9db0-43e7-8286-7b46cc3a37ed)  
  
