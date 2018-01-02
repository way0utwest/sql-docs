---
title: "getUser Method (SQLServerDataSource) | Microsoft Docs"
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
  - "SQLServerDataSource.getUser"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 3513dd7f-6ae5-4010-bde0-454ac4365bce
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getUser Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns the user name that is used to connect the data source.  
  
## Syntax  
  
```  
  
public java.lang.String getUser()  
```  
  
## Return Value  
 A **String** that contains the user name.  
  
## Remarks  
 The [setUser](../../../connect/jdbc/reference/setuser-method-sqlserverdatasource.md) method sets the user name that will be used when connecting to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]. If user name value is not set, the getUser method returns the default value of null.  
  
## See Also  
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
