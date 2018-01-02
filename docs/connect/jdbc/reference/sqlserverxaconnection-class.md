---
title: "SQLServerXAConnection Class | Microsoft Docs"
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
ms.assetid: 5ecb4bf1-b8d1-47cf-9cb1-7a18acc11ce2
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLServerXAConnection Class
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Represents JDBC connections that can participate in distributed (XA) transactions.  
  
 **Package:** com.microsoft.sqlserver.jdbc  
  
 **Extends:** [SQLServerPooledConnection](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md)  
  
 **Implements:** javax.sql.XAConnection  
  
## Syntax  
  
```  
  
public class SQLServerXAConnection  
```  
  
## Remarks  
 A SQLServerXAConnection object can be enlisted in a distributed transaction by means of an [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) object. A transaction manager, usually part of a middle tier server, manages a SQLServerXAConnection object through the SQLServerXAResource object.  
  
> [!NOTE]  
>  Application programmers typically do not use this interface directly. It is primarily used by a transaction manager working in the middle tier server.  
  
## See Also  
 [SQLServerXAConnection Members](../../../connect/jdbc/reference/sqlserverxaconnection-members.md)   
 [JDBC Driver API Reference](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
