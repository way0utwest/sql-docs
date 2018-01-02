---
title: "SQLServerXADataSource Class | Microsoft Docs"
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
ms.assetid: 95fc7b07-2498-4a7e-8f7f-ee0d86b598b4
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLServerXADataSource Class
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Represents a factory for [SQLServerXAConnection](../../../connect/jdbc/reference/sqlserverxaconnection-class.md) objects that is used internally.  
  
 **Package:** com.microsoft.sqlserver.jdbc  
  
 **Extends:** [SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-class.md)  
  
 **Implements:** javax.sql.XADataSource  
  
## Syntax  
  
```  
  
public class SQLServerXADataSource  
```  
  
## Remarks  
 An object that implements the SQLServerXADataSource interface is typically registered with a naming service that uses the Java Naming and Directory Interface (JNDI).  
  
 The SQLServerXADataSource class provides database connections for use in distributed (XA) transactions. The SQLServerXADataSource class also supports connection pooling of physical connections. The SQLServerXADataSource and SQLServerXAConnection interfaces, which are defined in the package javax.sql, are implemented by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)].  
  
 A SQLServerXAConnection object is a pooled connection that can participate in a distributed transaction. More precisely, SQLServerXAConnection extends the SQLServerPooledConnection interface by adding the method [getXAResource](../../../connect/jdbc/reference/getxaresource-method-sqlserverxaconnection.md). This method produces a [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) object that can be used by a transaction manager to coordinate the work done on this connection with the other participants in the distributed transaction. Because they extend the SQLServerPooledConnection interface, SQLServerXAConnection objects support all the methods of SQLServerPooledConnection objects. They are reusable physical connections to an underlying data source and produce logical connection handles that can be passed back to a JDBC application.  
  
 SQLServerXAConnection objects are produced by a SQLServerXADataSource object. SQLServerConnectionPoolDataSource objects and SQLServerXADataSource objects are similar because they are both implemented below a data source layer that is visible to the JDBC application. This architecture lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] support distributed transactions in a way that is transparent to the application. SQLServerXADataSource can be configured to integrate with [!INCLUDE[msCoName](../../../includes/msconame_md.md)] Distributed Transaction Coordinator (DTC) to provide true, distributed transaction processing.  
  
## See Also  
 [SQLServerXADataSource Members](../../../connect/jdbc/reference/sqlserverxadatasource-members.md)   
 [JDBC Driver API Reference](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
