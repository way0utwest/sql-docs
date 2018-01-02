---
title: "nativeSQL Method (SQLServerConnection) | Microsoft Docs"
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
  - "SQLServerConnection.nativeSQL"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 2188a6e1-792f-47bd-b207-1d01741231b2
caps.latest.revision: 14
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# nativeSQL Method (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Converts the given SQL statement into the native SQL grammar of the database server.  
  
> [!NOTE]  
>  This method is not currently supported by the [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)].  
  
## Syntax  
  
```  
  
public java.lang.String nativeSQL(java.lang.String sql)  
```  
  
#### Parameters  
 *sql*  
  
 A **String** containing an SQL statement.  
  
## Return Value  
 A **String** containing the converted SQL statement.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This nativeSQL method is specified by the nativeSQL method in the java.sql.Connection interface.  
  
## See Also  
 [SQLServerConnection Members](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection Class](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
