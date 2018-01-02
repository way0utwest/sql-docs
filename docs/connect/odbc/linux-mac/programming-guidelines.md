---
title: "Programming Guidelines | Microsoft Docs"
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
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Programming Guidelines

[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]

The programming features of the [!INCLUDE[msCoName](../../../includes/msconame_md.md)] ODBC Driver 13 and 13.1 for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] on macOS and Linux are based on ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Native Client ([SQL Server Native Client (ODBC)](http://go.microsoft.com/fwlink/?LinkID=134151)). [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Native Client is based on ODBC in Windows Data Access Components ([ODBC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkID=45250)).  

An ODBC application can use Multiple Active Result Sets (MARS) and other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] specific features by including `/usr/local/include/msodbcsql.h` after including the unixODBC headers (`sql.h`, `sqlext.h`, `sqltypes.h`, and `sqlucode.h`). Then use the same symbolic names for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]-specific items that you would in your Windows ODBC applications.  

## Available Features  
The following sections from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Native Client documentation for ODBC ([SQL Server Native Client (ODBC)](http://go.microsoft.com/fwlink/?LinkID=134151)) are valid when using the ODBC driver on macOS and Linux:  

-   [Communicating with SQL Server (ODBC)](http://msdn.microsoft.com/library/ms131692.aspx)  
-   [Connection and query timeout support](http://msdn.microsoft.com/library/ms130822.aspx)  
-   [Cursors](http://msdn.microsoft.com/library/ms130794(SQL.110).aspx)  
-   [Date/Time Improvements (ODBC)](http://msdn.microsoft.com/library/bb677319.aspx)  
-   [Executing Queries (ODBC)](http://msdn.microsoft.com/library/ms131677.aspx)  
-   [Handling Errors and Messages](http://msdn.microsoft.com/library/ms131289.aspx)  
-   [Kerberos authentication](http://msdn.microsoft.com/library/cc280459.aspx)  
-   [Large CLR User-Defined Types (ODBC)](http://msdn.microsoft.com/library/bb677316.aspx)  
-   [Performing Transactions (ODBC) (except distributed transactions)](http://msdn.microsoft.com/library/ms131706.aspx)  
-   [Processing Results (ODBC)](http://msdn.microsoft.com/library/ms130812.aspx)  
-   [Running Stored Procedures](http://msdn.microsoft.com/library/ms131440.aspx)
-   [Sparse Columns Support (ODBC)](http://msdn.microsoft.com/library/cc280357.aspx)
-   [SSL encryption](http://msdn.microsoft.com/library/ms131691.aspx)
-   [Table Valued Parameters](https://docs.microsoft.com/en-us/sql/relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc)
-   [UTF-8 and UTF-16 for command and data API](http://msdn.microsoft.com/library/ff878241.aspx)
-   [Using Catalog Functions](http://msdn.microsoft.com/library/ms131490.aspx)  

## Unsupported Features

The following features have not been verified to work correctly in this release of the ODBC driver on macOS and Linux:

-   Failover Cluster Connection
-   [Transparent Network IP Resolution](https://docs.microsoft.com/en-us/sql/connect/odbc/linux/using-transparent-network-ip-resolution)
-   [Advanced Driver Tracing](https://blogs.msdn.microsoft.com/mattn/2012/05/15/enabling-advanced-driver-tracing-for-the-sql-native-client-odbc-drivers/)

The following features are not available in this release of the ODBC driver on macOS and Linux: 

-   Distributed Transactions (SQL_ATTR_ENLIST_IN_DTC attribute is not supported)  
-   Database Mirroring  
-   FILESTREAM  
-   Profiling ODBC driver performance, discussed in [SQLSetConnectAttr](http://go.microsoft.com/fwlink/?LinkId=234099), and the following performance-related connection attributes:  
    -   SQL_COPT_SS_PERF_DATA  
    -   SQL_COPT_SS_PERF_DATA_LOG  
    -   SQL_COPT_SS_PERF_DATA_LOG_NOW  
    -   SQL_COPT_SS_PERF_QUERY  
    -   SQL_COPT_SS_PERF_QUERY_INTERVAL  
    -   SQL_COPT_SS_PERF_QUERY_LOG  
-   SQLBrowseConnect  
-   C interval types such as SQL_C_INTERVAL_YEAR_TO_MONTH (documented in [Data Type Identifiers and Descriptors](http://msdn.microsoft.com/library/ms716351(VS.85).aspx))
-   The SQL_CUR_USE_ODBC value of the SQL_ATTR_ODBC_CURSORS attribute of the SQLSetConnectAttr function.

## Character Set Support

SQLCHAR data in one of the following character sets is supported by the driver:

  -  UTF-8
  -  CP437
  -  CP850
  -  CP874
  -  CP932
  -  CP936
  -  CP949
  -  CP950
  -  CP1251
  -  CP1253
  -  CP1256
  -  CP1257
  -  CP1258
  -  ISO-8859-1 / CP1252
  -  ISO-8859-2 / CP1250
  -  ISO-8859-3
  -  ISO-8859-4
  -  ISO-8859-5
  -  ISO-8859-6
  -  ISO-8859-7
  -  ISO-8859-8 / CP1255
  -  ISO-8859-9 / CP1254
  -  ISO-8859-13
  -  ISO-8859-15

Upon connection, the driver detects the current locale of the process it is loaded in. If it is one of the supported encodings above, the driver will use that encoding for SQLCHAR (narrow-character) data; otherwise, it defaults to UTF-8. Since all processes start in the "C" locale by default (and thus cause the driver to default to UTF-8), if an application needs to use one of the encodings above, it should use the **setlocale** function to set the locale appropriately before connecting; either by specifying the desired locale explicitly, or using an empty string e.g. `setlocale(LC_ALL, "")`, to use the locale settings of the environment.

SQLWCHAR data must be UTF-16LE (Little Endian).

If SQLDescribeParameter does not specify a SQL type on the server, the driver uses the SQL type specified in the *ParameterType* parameter of SQLBindParameter. If a narrow character SQL type, such as SQL_VARCHAR, is specified in SQLBindParameter, the driver converts the supplied data from the client code page to the default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] code page. (The default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] code page is typically 1252.) If the client code page is not supported, it will be set to UTF-8. In this case, the driver then converts the UTF-8 data to the default code page. However, data loss is possible. If code page 1252 cannot represent a character, the driver converts the character to a question mark ('?'). To avoid this data loss, specify a Unicode SQL character type, such as SQL_NVARCHAR, in SQLBindParameter. In this case, the driver converts the supplied Unicode data in UTF-8 encoding to UTF-16 without loss of data.

There is a text-encoding conversion difference between Windows and several versions of the iconv library on Linux and macOS. Text data that is encoded in codepage 1255 (Hebrew) has one code point (0xCA) that behaves differently upon conversion. Converting this character to Unicode on Windows produces a UTF-16 code point of 0x05BA. Converting to Unicode on macOS and Linux with libiconv versions earlier than 1.15 produces a UTF-16 code point of 0x00CA.

When UTF-8 multibyte characters or UTF-16 surrogates are split across SQLPutData buffers, it results in data corruption. Use buffers for streaming SQLPutData that do not end in partial character encodings.  

## Additional Notes  

1.  You can make a dedicated administrator connection (DAC) using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] authentication and **host,port**. A member of the Sysadmin role first needs to discover the DAC port. See [Diagnostic Connection for Database Administrators](https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/diagnostic-connection-for-database-administrators#dac-port) to discover how. For example, if the DAC port were 33000, you could connect to it with `sqlcmd` as follows:  

    ```
    sqlcmd –U <user> -P <pwd> -S <host>,33000
    ```

    > [!NOTE]  
    > DAC connections must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Authentication.  
    
2.  The UnixODBC driver manager returns "invalid attribute/option identifier" for all statement attributes when they are passed through SQLSetConnectAttr. On Windows, when SQLSetConnectAttr receives a statement attribute value, it causes the driver to set that value on all active statements which are children of the connection handle.  

## See Also  
[Frequently Asked Questions](../../../connect/odbc/linux-mac/frequently-asked-questions-faq-for-odbc-linux.md)

[Known Issues in this Version of the Driver](../../../connect/odbc/linux-mac/known-issues-in-this-version-of-the-driver.md)

[Release Notes](../../../connect/odbc/linux-mac/release-notes.md)
