---
title: "SQLServerParameterMetaData Class | Microsoft Docs"
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
ms.assetid: 546290e0-9411-4a2b-aa36-61251e70e9cf
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLServerParameterMetaData Class
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Represents the metadata for prepared statement parameters.  
  
 **Package:** com.microsoft.sqlserver.jdbc  
  
 **Extends:** java.lang.Object  
  
 **Implements:** java.sql.ParameterMetaData  
  
## Syntax  
  
```  
  
public class SQLServerParameterMetaData  
```  
  
## Remarks  
 To retrieve parameter metadata, prepared statements are run with SET FMT ONLY. Callable statements call sp_sproc_columns to retrieve names and metadata for the procedure parameters.  
  
## See Also  
 [SQLServerParameterMetaData Members](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [JDBC Driver API Reference](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
