---
title: "getGeneratedKeys Method (SQLServerStatement) | Microsoft Docs"
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
  - "SQLServerStatement.getGeneratedKeys"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: a3325950-0e81-4ae8-aa0c-e1f6d371adcd
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getGeneratedKeys Method (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves any auto-generated keys that are created as a result of running this [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) object.  
  
## Syntax  
  
```  
  
public final java.sql.ResultSet getGeneratedKeys()  
```  
  
## Return Value  
 A ResultSet object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getGeneratedKeys method is specified by the getGeneratedKeys method in the java.sql.Statement interface.  
  
 For more information about how to use this method, see [Using Auto Generated Keys](../../../connect/jdbc/using-auto-generated-keys.md).  
  
## See Also  
 [SQLServerStatement Members](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement Class](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
