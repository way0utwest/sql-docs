---
title: "commit Method (SQLServerXAResource) | Microsoft Docs"
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
  - "SQLServerXAResource.commit"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 1d0f8612-fb4a-4eca-bc37-8342e1419fd4
caps.latest.revision: 7
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# commit Method (SQLServerXAResource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Commits the global transaction that is specified by the given Xid object.  
  
## Syntax  
  
```  
  
public void commit(javax.transaction.xa.Xid xid,  
                   boolean onePhase)  
```  
  
#### Parameters  
 *xid*  
  
 An Xid object.  
  
 *onePhase*  
  
 A **boolean** value.  
  
## Exceptions  
 javax.transaction.xa.XAException  
  
## Remarks  
 This commit method is specified by the commit method in the javax.transaction.xa.XAResource interface.  
  
## See Also  
 [SQLServerXAResource Methods](../../../connect/jdbc/reference/sqlserverxaresource-methods.md)   
 [SQLServerXAResource Members](../../../connect/jdbc/reference/sqlserverxaresource-members.md)   
 [SQLServerXAResource Class](../../../connect/jdbc/reference/sqlserverxaresource-class.md)  
  
  
