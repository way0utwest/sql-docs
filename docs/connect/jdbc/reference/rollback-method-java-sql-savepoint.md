---
title: "rollback Method (java.sql.Savepoint) | Microsoft Docs"
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
  - "SQLServerConnection.rollback (java.sql.Savepoint)"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: d5dbd9ef-194f-4130-bfcc-7901a4fa8ded
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# rollback Method (java.sql.Savepoint)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Undoes all changes made after the given [SQLServerSavepoint](../../../connect/jdbc/reference/sqlserversavepoint-class.md) object was set.  
  
## Syntax  
  
```  
  
public void rollback(java.sql.Savepoint s)  
```  
  
#### Parameters  
 *s*  
  
 The SavePoint object to rollback to.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This rollBack method is specified by the rollBack method in the java.sql.Connection interface.  
  
 This method should be used only when auto-commit mode has been disabled.  
  
## See Also  
 [rollback Method &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/rollback-method-sqlserverconnection.md)   
 [SQLServerConnection Members](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection Class](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
