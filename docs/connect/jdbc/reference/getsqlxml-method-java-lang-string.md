---
title: "getSQLXML Method (java.lang.String) | Microsoft Docs"
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
ms.assetid: f56b192a-3255-4215-b552-8e494fbca083
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getSQLXML Method (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves the value of the designated parameter as a SQLXML object given the parameter name.  
  
## Syntax  
  
```  
  
public final java.sql.SQLXML getSQLXML(java.lang.String parameterName)  
```  
  
#### Parameters  
 *parameterName*  
  
 A **String** that indicates the parameter name.  
  
## Return Value  
 ASQLXMLobject.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getSQLXML method is specified by the getSQLXML method in the java.sql.CallableStatement interface.  
  
## See Also  
 [getSQLXML Method &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getsqlxml-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement Members](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
