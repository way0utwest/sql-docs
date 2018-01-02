---
title: "updateRef Method (java.lang.String, java.sql.Ref) | Microsoft Docs"
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
  - "SQLServerResultSet.updateRef (java.lang.String, java.sql.Ref)"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 7740d17d-282f-4f1d-91f9-c68a873b069a
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# updateRef Method (java.lang.String, java.sql.Ref)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Updates the designated column with a java.sql.Ref value given the column name.  
  
## Syntax  
  
```  
  
public void updateRef(java.lang.String columnName,  
                      java.sql.Ref x)  
```  
  
#### Parameters  
 *columnName*  
  
 A **String** that contains the column name.  
  
 *x*  
  
 A Ref object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This updateRef method is specified by the updateRef method in the java.sql.ResultSet interface.  
  
## See Also  
 [updateRef Method &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updateref-method-sqlserverresultset.md)   
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
