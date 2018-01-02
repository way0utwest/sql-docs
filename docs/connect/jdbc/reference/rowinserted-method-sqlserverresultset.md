---
title: "rowInserted Method (SQLServerResultSet) | Microsoft Docs"
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
  - "SQLServerResultSet.rowInserted"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: e7c10372-0be8-4baa-87f7-ed6b66003357
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# rowInserted Method (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves whether the current row has had an insertion.  
  
## Syntax  
  
```  
  
public boolean rowInserted()  
```  
  
## Return Value  
 **true** if a row has had an insertion and insertions are detected. Otherwise, **false**.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This rowUpdated method is specified by the rowUpdated method in the java.sql.ResultSet interface.  
  
 The value that is returned depends on whether this [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) object can detect visible inserts.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] does not detect inserted rows for any cursor type.  
  
## See Also  
 [SQLServerResultSet Members](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet Class](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
