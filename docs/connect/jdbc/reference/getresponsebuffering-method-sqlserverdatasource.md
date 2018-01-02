---
title: "getResponseBuffering Method (SQLServerDataSource) | Microsoft Docs"
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
  - "SQLServerDataSource.getResponseBuffering()"
apilocation: 
  - "SQLServerDataSource.getResponseBuffering()"
apitype: "Assembly"
ms.assetid: 19585a93-88a4-415e-a20e-12ba58cddeaa
caps.latest.revision: 27
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getResponseBuffering Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns the response buffering mode for this [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) object.  
  
## Syntax  
  
```  
  
public java.lang.String getResponseBuffering()  
```  
  
## Return Value  
 A **String** that contains a lower-case **full** or **adaptive**.  
  
## Remarks  
 The **full** value specifies reading the entire result from the server at run time.  
  
 The **adaptive** value specifies buffering the minimum possible data when necessary. The **adaptive** value is the default buffering mode.  
  
 For more information about using the response buffering mode, see [Using Adaptive Buffering](../../../connect/jdbc/using-adaptive-buffering.md).  
  
## See Also  
 [setResponseBuffering Method &#40;SQLServerDataSource&#41;](../../../connect/jdbc/reference/setresponsebuffering-method-sqlserverdatasource.md)   
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
