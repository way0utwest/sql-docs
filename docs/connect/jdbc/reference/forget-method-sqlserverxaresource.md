---
title: "forget Method (SQLServerXAResource) | Microsoft Docs"
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
  - "SQLServerXAResource.forget"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 6d83138d-aa45-4d94-9da6-fdfe7ed28edc
caps.latest.revision: 7
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# forget Method (SQLServerXAResource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Tells the resource manager to forget about a heuristically completed transaction branch.  
  
## Syntax  
  
```  
  
public void forget(javax.transaction.xa.Xid xid)  
```  
  
#### Parameters  
 *xid*  
  
 An Xid object.  
  
## Exceptions  
 javax.transaction.xa.XAException  
  
## Remarks  
 This forget method is specified by the forget method in the javax.transaction.xa.XAResource interface.  
  
## See Also  
 [SQLServerXAResource Methods](../../../connect/jdbc/reference/sqlserverxaresource-methods.md)   
 [SQLServerXAResource Members](../../../connect/jdbc/reference/sqlserverxaresource-members.md)   
 [SQLServerXAResource Class](../../../connect/jdbc/reference/sqlserverxaresource-class.md)  
  
  
