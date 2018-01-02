---
title: "absolute Method (SQLServerResultSet) | Microsoft Docs"
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
  - "SQLServerResultSet.absolute"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 638e8148-8ca0-4e1f-9ec2-04a11bc9809b
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# absolute Method (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Moves the cursor to the given row in this [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) object.  
  
## Syntax  
  
```  
  
public boolean absolute(int row)  
```  
  
#### Parameters  
 *row*  
  
 An **int** that indicates the row number to move to. Can be positive, negative, or 0.  
  
## Return Value  
 **true** if the cursor is moved to the given position. **false** if it is before the first row or after the last row.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This absolute method is specified by the absolute method in the java.sql.ResultSet interface.  
  
## See Also  
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
