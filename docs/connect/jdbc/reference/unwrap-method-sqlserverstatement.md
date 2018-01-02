---
title: "unwrap Method (SQLServerStatement) | Microsoft Docs"
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
ms.assetid: ce680176-ef04-4e44-bb6c-ec50bd06e7e6
caps.latest.revision: 22
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# unwrap Method (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns an object that implements the specified interface to allow access to the [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]-specific methods.  
  
## Syntax  
  
```  
  
public <T> T unwrap(Class<T> iface)  
```  
  
#### Parameters  
 *iface*  
  
 A class of type **T** defining an interface.  
  
## Return Value  
 An object that implements the specified interface.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 The [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverstatement.md) method is defined by the java.sql.Wrapper interface, which is introduced in the JDBC 4.0 Spec.  
  
 Applications might need to access extensions to the JDBC API that are specific to the [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]. The unwrap method supports unwrapping to public classes that this object extends, if the classes expose vendor extensions.  
  
 When this method is called, the object unwraps to the [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) class.  
  
 For example code, see [Updating Large Data Sample](../../../connect/jdbc/updating-large-data-sample.md), or [unwrap Method &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/unwrap-method-sqlservercallablestatement.md).  
  
 For more information, see [Wrappers and Interfaces](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## See Also  
 [isWrapperFor Method &#40;SQLServerStatement&#41;](../../../connect/jdbc/reference/iswrapperfor-method-sqlserverstatement.md)   
 [SQLServerStatement Members](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement Class](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
