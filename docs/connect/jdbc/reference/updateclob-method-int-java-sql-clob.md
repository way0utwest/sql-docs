---
title: "updateClob Method (int, java.sql.Clob) | Microsoft Docs"
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
  - "SQLServerResultSet.updateClob (int, java.sql.Clob)"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: d2a5e9cb-2631-4f6e-a90c-4bee58e2f7b8
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# updateClob Method (int, java.sql.Clob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Updates the designated column with a java.sql.Clob value given the column index.  
  
## Syntax  
  
```  
  
public void updateClob(int columnIndex,  
                       java.sql.Clob clobValue)  
```  
  
#### Parameters  
 *columnIndex*  
  
 An **int** that indicates the column index.  
  
 *clobValue*  
  
 A Clob object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This updateClob method is specified by the updateClob method in the java.sql.ResultSet interface.  
  
## See Also  
 [updateClob Method &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updateclob-method-sqlserverresultset.md)   
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
