---
title: "updateAsciiStream Method (java.io.InputStream) | Microsoft Docs"
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
ms.assetid: 747b0308-1ce6-4eba-bdfc-af29c21c18cf
caps.latest.revision: 17
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# updateAsciiStream Method (java.lang.String, java.io.InputStream)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Updates the designated column with an ASCII stream value.  
  
## Syntax  
  
```  
  
public void updateAsciiStream(java.lang.String columnLabel,  
                              java.io.InputStream x)  
```  
  
#### Parameters  
 *columnLabel*  
  
 A **String** that contains the column label.  
  
 *x*  
  
 An InputStream object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This updateAsciiStream method is specified by the updateAsciiStream method in the java.sql.ResultSet interface.  
  
 This method passes ASCII characters (bytes) from an InputStream object to convertible character columns, which are the ASCII range [0x00 – 0x7F] of Unicode, and 874, 932, 936, 949, 950, and 1250 through 1258 code pages. This method performs a conversion to the destination collation page. Trying to update an unconvertible destination column will cause an exception to be thrown. For binary columns, raw bytes are passed.  
  
 Using this method for the **image**, **text**, and **ntext**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] data types might impact performance.  
  
## See Also  
 [updateAsciiStream Method &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md)   
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
