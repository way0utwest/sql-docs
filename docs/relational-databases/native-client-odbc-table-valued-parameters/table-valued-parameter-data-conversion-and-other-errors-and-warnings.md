---
title: "Table-Valued Parameter Data Conversion and Other Errors and Warnings | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "native-client-odbc-table-valued-parameters"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "table-valued parameters (ODBC), data conversion"
  - "table-valued parameters (ODBC), error messages"
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
caps.latest.revision: 13
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Table-Valued Parameter Data Conversion and Other Errors and Warnings
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values. But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.  
  
 When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record. The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number. An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings. These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.  
  
 The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects. That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non–table-valued parameters.  
  
## See Also  
 [Table-Valued Parameters &#40;ODBC&#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
  
