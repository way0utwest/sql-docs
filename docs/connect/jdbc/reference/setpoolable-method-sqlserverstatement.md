---
title: "setPoolable Method (SQLServerStatement) | Microsoft Docs"
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
ms.assetid: f0f798c8-cafb-4acc-b85d-2e0059c91d92
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# setPoolable Method (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Requests that a statement be pooled or not pooled.  
  
## Syntax  
  
```  
  
public void setPoolable(boolean poolable) throws SQLException  
```  
  
#### Parameters  
 *poolable*  
  
 If **true**, requests that the statement be pooled. If **false**, requests that the statement not be pooled.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 The value specified in the *poolable* parameter is a hint to the statement pool implementation indicating if the application wants the statement to be pooled. The statement pool manager decides if it will use the hint.  
  
 A statement's pool value applies to both internal statement caches implemented by the driver and external statement caches implemented by application servers and other applications.  
  
 By default, a SQLServerStatement object is not poolable when created. SQLServerPreparedStatement and SQLServerCallableStatement objects are poolable when created.  
  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md) is thrown if this method is called on a closed statement.  
  
 [isPoolable](../../../connect/jdbc/reference/ispoolable-method-sqlserverstatement.md) returns a value indicating if the object is poolable.  
  
## See Also  
 [SQLServerStatement Members](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement Class](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
