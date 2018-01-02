---
title: "rowDeleted Method (SQLServerResultSet) | Microsoft Docs"
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
  - "SQLServerResultSet.rowDeleted"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 9c6db315-e614-4604-b020-41af6a214cc1
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# rowDeleted Method (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves whether a row has been deleted.  
  
## Syntax  
  
```  
  
public boolean rowDeleted()  
```  
  
## Return Value  
 **true** if a row was deleted and deletions are detected. Otherwise, **false**.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This rowDeleted method is specified by the rowDeleted method in the java.sql.ResultSet interface.  
  
 A deleted row might leave a visible hole in a result set. This method can be used to detect holes in a result set. The value that is returned depends on whether this [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) object can detect deletions.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] detects deleted rows for all updatable cursor types, though the detection is transient for forward and dynamic cursors.  
  
## See Also  
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
