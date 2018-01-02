---
title: "Data Migration Report  (MySQLToSQL) | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssma-mysql"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "sql-ssma"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Azure SQL Database"
  - "SQL Server"
ms.assetid: 5524a575-67dd-4ef6-9d17-3412df9b9f9c
caps.latest.revision: 4
author: "Shamikg"
ms.author: "Shamikg"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Data Migration Report  (MySQLToSQL)
The **Data Migration Report** dialog box appears after you migrate data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
## Options  
**Status**  
Shows the status of the data migration from the source to the target database.  
  
**From**  
The source table.  
  
**To**  
The target table.  
  
**Total Number of Rows**  
The number of rows of data in the source table.  
  
**Number of Successfully Migrated Rows**  
The number of rows of data successfully migrated to the target table.  
  
**Ratio**  
The percentage of rows successfully migrated.  
  
**Details**  
If any data migration failed, click to display migration details for the selected row in the report. SSMA will display the reason for the failure.  
  
**Save Report**  
Saves the report to a .CSV, (comma-separated values) file, which can be examined using Microsoft Excel.  
  
