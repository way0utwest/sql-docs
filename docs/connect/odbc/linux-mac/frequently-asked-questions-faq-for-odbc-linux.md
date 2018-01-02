---
title: "Frequently Asked Questions (FAQ) for ODBC Linux and macOS | Microsoft Docs"
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
ms.assetid: 65bfd6d2-c83d-4528-a5e1-a85b125a4f4a
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Frequently Asked Questions (FAQ) for ODBC Linux and macOS
[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]

The following are answers to questions about the ODBC Driver for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] on Linux and macOS.
  
## Frequently Asked Questions

**How do existing ODBC applications on Linux or macOS work with the driver?**  
You should be able to compile and run the ODBC applications that you have been compiling and running on Linux or macOS using other drivers. 
  
**Which features of [!INCLUDE[ssSQL11](../../../includes/sssql11_md.md)] does this version of the driver support?**

The ODBC driver on Linux and macOS supports all server features in [!INCLUDE[ssSQL11](../../../includes/sssql11_md.md)] except LocalDB. For more information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] supported features, see [Programming Guidelines](../../../connect/odbc/linux-mac/programming-guidelines.md).  
  
**Does the driver support Kerberos authentication?**  
Yes. If you have an existing Kerberos environment setup, you should be able to connect to servers using the `Trusted_Connection=Yes` DSN or connection string option. For more information, see [Using Integrated Authentication](../../../connect/odbc/linux-mac/using-integrated-authentication.md).  
  
**Which Unicode encoding should an application use?**  
UTF-8 for SQL_CHAR data and UTF-16 for SQL_WCHAR data.  

**Are there ODBC samples that I can download and run with the driver to experiment with or evaluate it?**

See [Use Existing MSDN C++ ODBC Samples for the ODBC Driver on Linux](http://blogs.msdn.com/b/sqlblog/archive/2012/01/26/use-existing-msdn-c-odbc-samples-for-microsoft-linux-odbc-driver.aspx) for a sample. This is also applicable to the macOS ODBC driver. 

**Is the ODBC driver on Linux or macOS open source?**

No, the ODBC drivers on Linux and macOS are not an open source product.  

## See Also
[Installing the Microsoft ODBC Driver for SQL Server on Linux and macOS](../../../connect/odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server.md)
