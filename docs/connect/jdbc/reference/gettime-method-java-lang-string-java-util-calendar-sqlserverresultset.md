---
title: "getTime Method (java.lang.String, java.util.Calendar) | Microsoft Docs"
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
  - "SQLServerResultSet.getTime (java.lang.String, java.util.Calendar)"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 13b51f77-cec9-45fc-862e-3d2bb2d718d7
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getTime Method (java.lang.String, java.util.Calendar) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves the value of the designated column name in the current row of this [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) object as a java.sql.Time object in the Java programming language, using the given Calendar object.  
  
## Syntax  
  
```  
  
public java.sql.Time getTime(java.lang.String colName,  
                             java.util.Calendar cal)  
```  
  
#### Parameters  
 *colName*  
  
 A **String** that contains the column name.  
  
 *cal*  
  
 A Calendar object.  
  
## Return Value  
 A Time object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getTime method is specified by the getTime method in the java.sql.ResultSet interface.  
  
 This method returns a valid time part of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] datetime or smalldatetime data type, with the date part set to the Java baseline date of 1970/01/01 in the supplied Calendar's timezone.  
  
## See Also  
 [getTime Method &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/gettime-method-sqlserverresultset.md)   
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
