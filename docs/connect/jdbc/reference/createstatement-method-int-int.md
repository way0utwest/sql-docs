---
title: "createStatement Method (int, int) | Microsoft Docs"
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
  - "SQLServerConnection.createStatement (int, int)"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 90dbf639-c3d8-4519-9300-5447c79aec17
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# createStatement Method (int, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Creates a [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) object that generates [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objects with the given type and concurrency.  
  
## Syntax  
  
```  
  
public java.sql.Statement createStatement(int resultSetType,  
                                          int resultSetConcurrency)  
```  
  
#### Parameters  
 *resultSetType*  
  
 The **int** value representing the result set type.  
  
 *resultSetConcurrency*  
  
 The **int** value representing the result set concurrency type.  
  
## Return Value  
 The Statement object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This createStatement method is specified by the createStatement method in the java.sql.Connection interface.  
  
## See Also  
 [createStatement Method &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/createstatement-method-sqlserverconnection.md)   
 [SQLServerConnection Members](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection Class](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
