---
title: "Importing Visual FoxPro Data into Microsoft Access | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "odbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "importing data [ODBC]"
  - "FoxPro ODBC driver [ODBC], Access"
  - "Visual FoxPro data [ODBC], Access"
  - "Visual FoxPro ODBC driver [ODBC], Access"
  - "Visual FoxPro data [ODBC], importing"
ms.assetid: a3591295-0a76-4e3c-b4fa-8bd4f1cde705
caps.latest.revision: 7
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Importing Visual FoxPro Data into Microsoft Access
You can import data stored in a Visual FoxPro database into a Microsoft Access database using the Import option.  
  
### To import Visual FoxPro data into a Microsoft Access database  
  
1.  Open a Microsoft Access database.  
  
2.  From the File menu, choose Get External Data then Import.  
  
3.  In the Import dialog box, select ODBC Databases in the Files of type list.  
  
4.  In the SQL Data Sources dialog box, select the Visual FoxPro data source that connects to the FoxPro data you want to query and click OK.  
  
5.  In the Import Objects dialog box, select one or more tables you want to import and click OK. The names of the Visual FoxPro tables you imported are displayed in the Tables tab of the Microsoft Access database.  
  
 You can now use Microsoft Access to manipulate the data in the imported Visual FoxPro tables. The data you import is a snapshot of the data stored in Visual FoxPro; changes you make to imported data are not sent back to the Visual FoxPro data source.  
  
 If you want changes you make in Microsoft Access to change the data on the Visual FoxPro data source, see [Querying and Updating Visual FoxPro Data from Microsoft Access](../../odbc/microsoft/querying-and-updating-visual-foxpro-data-from-microsoft-access.md).
