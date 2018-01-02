---
title: "getQueryTimeout Method (SQLServerStatement) | Microsoft Docs"
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
  - "SQLServerStatement.getQueryTimeout"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 8dff954f-b458-4fa6-abe6-be62ff75e2b9
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getQueryTimeout Method (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves the number of seconds [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] will wait for this [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) object to run.  
  
## Syntax  
  
```  
  
public final int getQueryTimeout()  
```  
  
## Return Value  
 An **int** that indicates the number of seconds that the JDBC driver will wait, or 0 if there is no limit.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getQueryTimeout method is specified by the getQueryTimeout method in the java.sql.Statement interface.  
  
## See Also  
 [SQLServerStatement Members](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement Class](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
