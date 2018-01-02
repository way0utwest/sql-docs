---
title: "SQLServerConnectionPoolDataSource Class | Microsoft Docs"
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
ms.assetid: b00e5a90-2af7-4d04-8ef8-256183777dcf
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLServerConnectionPoolDataSource Class
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Represents physical database connections for connection pool managers.  
  
 **Package:** com.microsoft.sqlserver.jdbc  
  
 **Extends:** [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
 **Implements:** javax.sql.ConnectionPoolDataSource  
  
## Syntax  
  
```  
  
public class SQLServerConnectionPoolDataSource  
```  
  
## Remarks  
 SQLServerConnectionPoolDataSource is typically used in Java Application Server environments that support built-in connection pooling and require a ConnectionPoolDataSource to provide physical connections, such as Java Platform, Enterprise Edition (Java EE) application servers that provide JDBC 3.0 API spec connection pooling.  
  
## See Also  
 [SQLServerConnectionPoolDataSource Members](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-members.md)   
 [JDBC Driver API Reference](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
