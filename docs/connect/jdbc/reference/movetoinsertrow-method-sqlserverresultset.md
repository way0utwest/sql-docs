---
title: "moveToInsertRow Method (SQLServerResultSet) | Microsoft Docs"
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
  - "SQLServerResultSet.moveToInsertRow"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: f3c54bfe-d5b7-4f6e-ae6c-3e8954e5b1c9
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# moveToInsertRow Method (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Moves the cursor to the insert row.  
  
## Syntax  
  
```  
  
public void moveToInsertRow()  
```  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This moveToInsertRow method is specified by the moveToInsertRow method in the java.sql.ResultSet interface.  
  
 The current cursor position is remembered while the cursor is positioned on the insert row. The insert row is a special row that is associated with an updatable result set. It is essentially a buffer where a new row can be constructed by calling the updater methods before adding the row to the result set.  
  
 Only the updater, getter, and [insertRow](../../../connect/jdbc/reference/insertrow-method-sqlserverresultset.md) methods can be called when the cursor is on the insert row. All the columns in a result set must be given a value each time this method is called, and before calling insertRow. An updater method must be called before a getter method can be called on a column value.  
  
## See Also  
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
