---
title: "isWrapperFor Method (SQLServerDataSource) | Microsoft Docs"
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
ms.assetid: f77af027-c021-4a17-b264-1ee592bfdd84
caps.latest.revision: 21
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# isWrapperFor Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Indicates whether this data source object is a wrapper for the specified interface.  
  
## Syntax  
  
```  
  
public boolean isWrapperFor(Class iface)  
```  
  
#### Parameters  
 *iface*  
  
 A **class** defining an interface.  
  
## Return Value  
 **true** if this object implements the interface or wraps an object that implements the interface. Otherwise, **false**.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 The [isWrapperFor](../../../connect/jdbc/reference/iswrapperfor-method-sqlserverdatasource.md) method and the [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverdatasource.md) method are defined by the java.sql.Wrapper interface, which is introduced in the JDBC 4.0 Spec.  
  
 If this method returns true, calling [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverdatasource.md) with the same argument will succeed.  
  
 For more information, see [Wrappers and Interfaces](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## See Also  
 [unwrap Method &#40;SQLServerDataSource&#41;](../../../connect/jdbc/reference/unwrap-method-sqlserverdatasource.md)   
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
