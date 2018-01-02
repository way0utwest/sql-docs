---
title: "Save an Execution Plan in XML Format | Microsoft Docs"
ms.custom: ""
ms.date: "08/21/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "performance"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XML query plans [SQL Server]"
  - "opening execution plans"
  - "XML Showplans [SQL Server]"
  - "execution plans [SQL Server], saving"
  - "saving execution plans"
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
caps.latest.revision: 25
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Save an Execution Plan in XML Format
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.  
  
 To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.  
  
### To save a query plan by using the XML Showplan SET options  
  
1.  In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Turn [SHOWPLAN_XML](../../t-sql/statements/set-showplan-xml-transact-sql.md) on with the following statement:  
  
    ```sql  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     To turn [STATISTICS XML](../../t-sql/statements/set-statistics-xml-transact-sql.md) on, use the following statement:  
  
    ```sql  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     > [!NOTE] 
     > SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query. This is also known as the **estimated** execution plan. 
     > STATISTICS XML generates runtime query execution plan information for a query, and executes the query. This is also known as the **actual** execution plan.  
  
3.  Execute a query. Example:  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.  
  
5.  In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.  
  
6.  In the **File name** box provide a name, in the format \<name**>.sqlplan**, and then click **Save**.  
  
### To save an execution plan by using SQL Server Management Studio options  
  
1.  Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]. For more information, see [Display the Estimated Execution Plan](../../relational-databases/performance/display-the-estimated-execution-plan.md) and [Display an Actual Execution Plan](../../relational-databases/performance/display-an-actual-execution-plan.md).  
  
2.  In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.  
  
     As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.  
  
3.  In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.  
  
4.  In the **File name** box provide a name, in the format \<name**>.sqlplan**, and then click **Save**.  
  
### To open a saved XML query plan in SQL Server Management Studio  
  
1.  In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.  
  
2.  In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.  
  
3.  Select the XML query plan file that you want to view, and click **Open**.  
  
     As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**. The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].  
  
## See Also  
 [SET SHOWPLAN_XML &#40;Transact-SQL&#41;](../../t-sql/statements/set-showplan-xml-transact-sql.md)   
 [SET STATISTICS XML &#40;Transact-SQL&#41;](../../t-sql/statements/set-statistics-xml-transact-sql.md)  
  
  
