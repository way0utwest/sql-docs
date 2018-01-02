---
title: "allTablesAreSelectable Method (SQLServerDatabaseMetaData) | Microsoft Docs"
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
  - "SQLServerDatabaseMetaData.allTablesAreSelectable"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: eb340450-45a7-49c8-84bc-1b9dd5ee842f
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# allTablesAreSelectable Method (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves whether the current user has permissions to use all the tables that are returned by the [getTables](../../../connect/jdbc/reference/gettables-method-sqlserverdatabasemetadata.md) method in a SELECT statement.  
  
## Syntax  
  
```  
  
public boolean allTablesAreSelectable()  
```  
  
## Return Value  
 **true** if the user has permissions to call use all the tables. Otherwise, **false**.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This allTablesAreSelectable method is specified by the allTablesAreSelectable method in the java.sql.DatabaseMetaData interface.  
  
## See Also  
 [SQLServerDatabaseMetaData Methods](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData Members](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData Class](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
