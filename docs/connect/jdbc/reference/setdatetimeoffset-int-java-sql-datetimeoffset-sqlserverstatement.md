---
title: "setDateTimeOffset(int, java.sql.DateTimeOffset) | Microsoft Docs"
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
ms.assetid: e8b6e380-6b53-489b-be73-73fcb5258269
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# setDateTimeOffset(int, java.sql.DateTimeOffset) (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Sets the designated parameter to the given DateTimeOffset value.  
  
## Syntax  
  
```  
  
public void setDateTimeOffset(int parameterIndex, DateTimeOffset dateTime)  
```  
  
#### Parameters  
 *parameterIndex*  
  
 Index of the column to set.  
  
 *dateTimeOffset*  
  
 A DateTimeOffset object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 The DateTimeOffset format is "YYYY-MM-DD HH-MM-SS[.nnnnnnn] [+][-] HH:MM". Use the following table for reference.  
  
|SQL Type|Insert|  
|--------------|------------|  
|datetime|May only insert: "YYYY-MM-DD hh:mm:ss[.nnn]"|  
|smalldatetime|May only insert: "YYYY-MM-DD hh:mm:ss"|  
|Time|May only insert: "hh:mm:ss[.nnnnnnn]"|  
|Date|May only insert: "YYYY-MM-DD"|  
|DateTime2|May only insert: "YYYY-MM-DD hh:mm:ss[.nnnnnnn]"|  
  
## See Also  
 [getDateTimeOffset &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getdatetimeoffset-sqlserverresultset.md)   
 [SQLServerStatement Members](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement Class](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
