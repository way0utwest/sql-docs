---
title: "Working with Data Types (JDBC) | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "jdbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b39f44d0-3710-4bc6-880c-35bd8c10a734
caps.latest.revision: 18
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
---
# Working with Data Types (JDBC)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  The primary function of the [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] is to allow Java developers to access data contained in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] databases. To accomplish this, the JDBC driver mediates the conversion between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] data types and Java language types and objects.  
  
> [!NOTE]  
>  For a detailed discussion of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] and JDBC driver data types, including their differences and how they are converted to Java language data types, see [Understanding the JDBC Driver Data Types](../../../connect/jdbc/understanding-the-jdbc-driver-data-types.md).  
  
 In order to work with SQL Server data types, the JDBC driver provides get\<Type> and set\<Type> methods for the [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) and [SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md) classes, and it provides get\<Type> and update\<Type> methods for the [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) class. Which method you use depends on the type of data that you are working with, and whether you are using result sets or queries.  
  
 The topics in this section describe how to use the JDBC driver data types to access [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] data in your Java applications.  
  
## In This Section  
  
|Topic|Description|  
|-----------|-----------------|  
|[Basic Data Types Sample](../../../connect/jdbc/basic-data-types-sample.md)|Describes how to use result set getter methods to retrieve basic [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] data type values, and how to use result set update methods to update those values.|  
|[SQLXML Data Type Sample](../../../connect/jdbc/sqlxml-data-type-sample.md)|Describes how to store an XML data in a relational database, how to retrieve an XML data from a database, and how to parse an XML data with the **SQLXML** Java data type.|  
  
## See Also  
 [Sample JDBC Driver Applications](../../../connect/jdbc/sample-jdbc-driver-applications.md)  
  
  
