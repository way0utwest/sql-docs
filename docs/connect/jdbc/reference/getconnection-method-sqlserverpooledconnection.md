---
title: "getConnection Method (SQLServerPooledConnection) | Microsoft Docs"
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
apiname: 
  - "SQLServerPooledConnection.getConnection"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 05bdb61f-26e8-480f-a1c1-1e46a8ed4b70
caps.latest.revision: 4
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getConnection Method (SQLServerPooledConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Creates an object handle for the physical connection that this [SQLServerPooledConnection](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md) object represents.  
  
## Syntax  
  
```  
  
public java.sql.Connection getConnection()  
```  
  
## Return Value  
 A Connection object.  
  
## Exceptions  
 java.sql.SQLException  
  
## Remarks  
 This getConnection method is specified by the getConnection method in the javax.sql.PooledConnection interface.  
  
## See Also  
 [SQLServerPooledConnection Methods](../../../connect/jdbc/reference/sqlserverpooledconnection-methods.md)   
 [SQLServerPooledConnection Members](../../../connect/jdbc/reference/sqlserverpooledconnection-members.md)   
 [SQLServerPooledConnection Class](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md)  
  
  
