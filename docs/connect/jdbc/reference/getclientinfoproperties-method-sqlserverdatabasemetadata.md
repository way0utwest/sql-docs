---
title: "getClientInfoProperties Method (SQLServerDatabaseMetaData) | Microsoft Docs"
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
ms.assetid: 1568aef4-f4c4-40a0-a1ab-9c106905bd92
caps.latest.revision: 14
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getClientInfoProperties Method (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves a list of the client information properties that the driver supports.  
  
## Syntax  
  
```  
  
public java.sql.ResultSet getClientInfoProperties()  
```  
  
## Return Value  
 A ResultSet object.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getClientInfoProperties method is specified by the getClientInfoProperties method in the java.sql.DatabaseMetaData interface.  
  
> [!NOTE]  
>  This method returns an empty result set. The driver supports setting only the **applicationName** and sets the **applicationName** only at connection time. SQL Server does not support updating the client application information after the connection is established.  
  
## See Also  
 [SQLServerDatabaseMetaData Members](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData Class](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
