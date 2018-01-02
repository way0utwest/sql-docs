---
title: "getRowIdLifetime Method (SQLServerDatabaseMetaData) | Microsoft Docs"
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
ms.assetid: 317c0b44-fe3f-4142-9cab-e40e4c4fe070
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getRowIdLifetime Method (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns a status indicating whether or not SQL RowId data type is supported. If supported, it returns the lifetime for which a RowId object remains valid.  
  
## Syntax  
  
```  
  
public java.sql.RowIdLifetime getRowIdLifetime()  
```  
  
## Return Value  
 A RowIdLifetime object.  
  
> [!NOTE]  
>  In the JDBC Driver version 2.0 release, this method returns java.sql.RowIdLifetime.ROWID_UNSUPPORTED value.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This getRowIdLifetime method is specified by the getRowIdLifetime method in the java.sql.DatabaseMetaData interface.  
  
## See Also  
 [SQLServerDatabaseMetaData Methods](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData Members](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData Class](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
