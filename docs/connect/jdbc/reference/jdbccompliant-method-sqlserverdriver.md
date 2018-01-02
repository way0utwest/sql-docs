---
title: "jdbcCompliant Method (SQLServerDriver) | Microsoft Docs"
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
  - "SQLServerDriver.jdbcCompliant"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: b299b20d-d1cd-45b3-91dc-dcf579498570
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# jdbcCompliant Method (SQLServerDriver)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Verifies that the [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] is compliant with the JDBC specification.  
  
## Syntax  
  
```  
  
public boolean jdbcCompliant()  
```  
  
## Return Value  
 **true** if the JDBC driver meets the minimum requirements. Otherwise, **false**.  
  
## Remarks  
 This jdbcCompliant method is specified by the jdbcCompliant method in the java.sql.Driver interface.  
  
## See Also  
 [SQLServerDriver Methods](../../../connect/jdbc/reference/sqlserverdriver-methods.md)   
 [SQLServerDriver Members](../../../connect/jdbc/reference/sqlserverdriver-members.md)   
 [SQLServerDriver Class](../../../connect/jdbc/reference/sqlserverdriver-class.md)  
  
  
