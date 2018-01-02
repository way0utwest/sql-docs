---
title: "recover Method (SQLServerXAResource) | Microsoft Docs"
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
  - "SQLServerXAResource.recover"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 840ecfcf-0dd3-4b7b-976f-dc9a96cd1464
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# recover Method (SQLServerXAResource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Obtains a list of prepared transaction branches from a resource manager.  
  
## Syntax  
  
```  
  
public javax.transaction.xa.Xid[] recover(int flags)  
```  
  
#### Parameters  
 *flags*  
  
 An **int** value that can take one of the following values: XAResource.TMSTARTRSCAN or XAResource.TMENDRSCAN or XAResource.TMNOFLAGS or XAResource.TMSTARTTRSCAN | XAResource.TMENDRSCAN.  
  
## Return Value  
 An Xid object.  
  
## Exceptions  
 javax.transaction.xa.XAException  
  
## Remarks  
 This recover method is specified by the recover method in the javax.transaction.xa.XAResource interface.  
  
 If the parameter **flag** is not XAResource.TMSTARTRSCAN or XAResource.TMSTARTRSCAN | XAResource.TMENDRSCAN, a recovery scan must be in progress.  
  
## See Also  
 [SQLServerXAResource Methods](../../../connect/jdbc/reference/sqlserverxaresource-methods.md)   
 [SQLServerXAResource Members](../../../connect/jdbc/reference/sqlserverxaresource-members.md)   
 [SQLServerXAResource Class](../../../connect/jdbc/reference/sqlserverxaresource-class.md)  
  
  
