---
title: "setClientInfo Method (java.util.Properties) | Microsoft Docs"
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
ms.assetid: b2a8ec0b-40a2-44d1-90d9-a810d4132e56
caps.latest.revision: 19
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# setClientInfo Method (java.util.Properties)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Sets the value of the connection's client information properties.  
  
## Syntax  
  
```  
  
public void setClientInfo (java.util.Properties properties)  
```  
  
#### Parameters  
 *properties*  
  
 A Properties object that contains the list of client information properties to set.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This setClientInfo method is specified by the setClientInfo method in the java.sql.Connection interface.  
  
 The [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] does not support any client information properties. This method generates warnings if the *properties* input parameter does not refer to an empty property set. In other words, this method generates warnings for the properties that the application wants to set. Applications should use [getWarnings](../../../connect/jdbc/reference/getwarnings-method-sqlserverconnection.md) method of the [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) class to retrieve each warning.  
  
## See Also  
 [setClientInfo Method &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/setclientinfo-method-sqlserverconnection.md)   
 [SQLServerConnection Members](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection Class](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
