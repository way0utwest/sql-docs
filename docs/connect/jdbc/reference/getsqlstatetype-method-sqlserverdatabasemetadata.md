---
title: "getSQLStateType Method (SQLServerDatabaseMetaData) | Microsoft Docs"
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
  - "SQLServerDatabaseMetaData.getSQLStateType"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: ee4d6751-68a3-4d04-831c-e6d704c59e63
caps.latest.revision: 17
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getSQLStateType Method (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Indicates whether the SQLSTATE that is returned by the SQLException.getSQLState method is X/Open (now known as Open Group) SQL CLI, SQL99 (JDBC 3.0), or SQL:2003 (JDBC 4.0).  
  
## Syntax  
  
```  
  
public int getSQLStateType()  
```  
  
## Return Value  
 An **int** that indicates the type of SQLSTATE, which can be one of the following values:  
  
-   For Java Runtime Environment version 5.0: If the **xopenStates** connection property is set to **true**, this method returns DatabaseMetaData.sqlStateXOpen. Otherwise, DatabaseMetaData.sqlStateSQL99.  
  
-   For Java Runtime Environment version 6.0: If the **xopenStates** connection property is set to **true**, this method returns DatabaseMetaData.sqlStateXOpen. Otherwise, DatabaseMetaData.sqlStateSQL.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getSQLStateType method is specified by the getSQLStateType method in the java.sql.DatabaseMetaData interface.  
  
## See Also  
 [SQLServerDatabaseMetaData Methods](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData Members](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData Class](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
