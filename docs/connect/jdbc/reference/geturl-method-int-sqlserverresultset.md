---
title: "getURL Method (int) (SQLServerResultSet) | Microsoft Docs"
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
  - "SQLServerResultSet.getURL (int)"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 5d0b665c-e1a7-43f7-88c3-db432773de7d
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getURL Method (int) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves the value of the designated column index in the current row of this [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) object as a URL object.  
  
## Syntax  
  
```  
  
public java.net.URL getURL(int columnIndex)  
```  
  
#### Parameters  
 *columnIndex*  
  
 An **int** that indicates the column index.  
  
## Return Value  
 A URL object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getURL method is specified by the getURL method in the java.sql.ResultSet interface.  
  
## See Also  
 [getURL Method &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/geturl-method-sqlserverresultset.md)   
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
