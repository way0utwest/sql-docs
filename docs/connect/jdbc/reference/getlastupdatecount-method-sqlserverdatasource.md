---
title: "getLastUpdateCount Method (SQLServerDataSource) | Microsoft Docs"
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
  - "SQLServerDataSource.getLastUpdateCount"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 4c4fbb24-0b02-42da-928c-a903bb591cc7
caps.latest.revision: 17
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getLastUpdateCount Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns a **Boolean** value that indicates if the lastUpdateCount property is enabled.  
  
## Syntax  
  
```  
  
public boolean getLastUpdateCount()  
```  
  
## Return Value  
 **true** if lastUpdateCount is enabled. Otherwise, **false**.  
  
## Remarks  
 If the lastUpdateCount property is set to **true**, the [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] will return only the last update count from an SQL statement passed to the server. If the lastUpdateCount property is set to **false**, the driver will return all update counts including those returned by any triggers that may have fired. If the lastUpdateCount property is not set, the getLastUpdateCount method returns the default value of **true**.  
  
## See Also  
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
