---
title: "Explicit Data Type Conversion Function | Microsoft Docs"
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
  - "explicit data type conversion functions [ODBC]"
  - "data type conversion functions [ODBC]"
  - "functions [ODBC], explicit data type conversion functions"
ms.assetid: d5789450-b668-4753-96c8-6789e955e7ed
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Explicit Data Type Conversion Function
Explicit data type conversion is specified in terms of SQL data type definitions.  
  
 The ODBC syntax for the explicit data type conversion function does not restrict conversions. The validity of specific conversions of one data type to another data type will be determined by each driver-specific implementation. The driver will, as it translates the ODBC syntax into the native syntax, reject those conversions that, although legal in the ODBC syntax, are not supported by the data source. The ODBC function **SQLGetInfo**, with the conversion options (such as SQL_CONVERT_BIGINT, SQL_CONVERT_BINARY, SQL_CONVERT_INTERVAL_YEAR_MONTH, and so on), provides a way to inquire about conversions supported by the data source.  
  
 The format of the **CONVERT** function is:  
  
 **CONVERT(** *value_exp*, *data_type***)**  
  
 The function returns the value specified by *value_exp* converted to the specified *data_type*, where *data_type* is one of the following keywords:  
  
|||  
|-|-|  
|SQL_BIGINT|SQL_INTERVAL_HOUR_TO_MINUTE|  
|SQL_BINARY|SQL_INTERVAL_HOUR_TO_SECOND|  
|SQL_BIT|SQL_INTERVAL_MINUTE_TO_SECOND|  
|SQL_CHAR|SQL_LONGVARBINARY|  
|SQL_DECIMAL|SQL_LONGVARCHAR|  
|SQL_DOUBLE|SQL_NUMERIC|  
|SQL_FLOAT|SQL_REAL|  
|SQL_GUID|SQL_SMALLINT|  
|SQL_INTEGER|SQL_DATE|  
|SQL_INTERVAL_MONTH|SQL_TIME|  
|SQL_INTERVAL_YEAR|SQL_TIMESTAMP|  
|SQL_INTERVAL_YEAR_TO_MONTH|SQL_TINYINT|  
|SQL_INTERVAL_DAY|SQL_VARBINARY|  
|SQL_INTERVAL_HOUR|SQL_VARCHAR|  
|SQL_INTERVAL_MINUTE|SQL_WCHAR|  
|SQL_INTERVAL_SECOND|SQL_WLONGVARCHAR|  
|SQL_INTERVAL_DAY_TO_HOUR|SQL_WVARCHAR|  
|SQL_INTERVAL_DAY_TO_MINUTE||  
|SQL_INTERVAL_DAY_TO_SECOND||  
  
 The ODBC syntax for the explicit data type conversion function does not support specification of conversion format. If specification of explicit formats is supported by the underlying data source, a driver must specify a default value or implement format specification.  
  
 The argument *value_exp* can be a column name, the result of another scalar function, or a numeric or string literal. For example:  
  
```  
{ fn CONVERT( { fn CURDATE() }, SQL_CHAR ) }  
```  
  
 converts the output of the CURDATE scalar function to a character string.  
  
 Because ODBC does not mandate a data type for return values from scalar functions (because the functions are often data source–specific), applications should use the CONVERT scalar function whenever possible to force data type conversion.  
  
 The following two examples illustrate the use of the **CONVERT** function. These examples assume the existence of a table called EMPLOYEES, with an EMPNO column of type SQL_SMALLINT and an EMPNAME column of type SQL_CHAR.  
  
 If an application specifies the following SQL statement:  
  
```  
SELECT EMPNO FROM EMPLOYEES WHERE {fn CONVERT(EMPNO,SQL_CHAR)} LIKE '1%'  
```  
  
-   A driver for ORACLE translates the SQL statement to:  
  
    ```  
    SELECT EMPNO FROM EMPLOYEES WHERE to_char(EMPNO) LIKE '1%'  
    ```  
  
-   A driver for SQL Server translates the SQL statement to:  
  
    ```  
    SELECT EMPNO FROM EMPLOYEES WHERE convert(char,EMPNO) LIKE '1%'  
    ```  
  
 If an application specifies the following SQL statement:  
  
```  
SELECT {fn ABS(EMPNO)}, {fn CONVERT(EMPNAME,SQL_SMALLINT)}  
   FROM EMPLOYEES WHERE EMPNO <> 0  
```  
  
-   A driver for ORACLE translates the SQL statement to:  
  
    ```  
    SELECT abs(EMPNO), to_number(EMPNAME) FROM EMPLOYEES WHERE EMPNO <> 0  
    ```  
  
-   A driver for SQL Server translates the SQL statement to:  
  
    ```  
    SELECT abs(EMPNO), convert(smallint, EMPNAME) FROM EMPLOYEES  
       WHERE EMPNO <> 0  
    ```  
  
-   A driver for Ingres translates the SQL statement to:  
  
    ```  
    SELECT abs(EMPNO), int2(EMPNAME) FROM EMPLOYEES WHERE EMPNO <> 0  
    ```
