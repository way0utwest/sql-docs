---
title: "getSendTimeAsDatetime Method (SQLServerDataSource) | Microsoft Docs"
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
ms.assetid: 02287122-5dc1-455d-987f-95fd9a69d503
caps.latest.revision: 15
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getSendTimeAsDatetime Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  This method was added in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0.  
  
 Returns the setting of the **sendTimeAsDatetime** connection property.  
  
## Syntax  
  
```  
  
public boolean getSendTimeAsDatetime();  
```  
  
## Return Value  
 **true** if java.sql.Time values will be sent to the server as a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] **datetime** type. **false** if java.sql.Time values will be sent to the server as a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] **time** type.  
  
## Remarks  
 See [Setting the Connection Properties](../../../connect/jdbc/setting-the-connection-properties.md) for more information about the **sendTimeAsDatetime** connection property.  
  
 [SQLServerDataSource.setSendTimeAsDatetime](../../../connect/jdbc/reference/setsendtimeasdatetime-method-sqlserverdatasource.md) lets you programmatically set the **sendTimeAsDatetime** connection property.  
  
 For more information, see [Configuring How java.sql.Time Values are Sent to the Server](../../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md).  
  
## See Also  
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
