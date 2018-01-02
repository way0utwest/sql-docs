---
title: "SQLServerXAResource Class | Microsoft Docs"
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
ms.assetid: df957b79-536f-4db7-b6ac-3d59343559fc
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLServerXAResource Class
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Represents an XAResource for XA distributed transaction management.  
  
 **Package:** com.microsoft.sqlserver.jdbc  
  
 **Extends:** java.lang.Object  
  
 **Implements:** javax.transaction.xa.XAResource  
  
## Syntax  
  
```  
  
public class SQLServerXAResource  
```  
  
## Remarks  
 XA transactions are implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] by using [!INCLUDE[msCoName](../../../includes/msconame_md.md)] Distributed Transaction Manager (DTC). The SQLServerXAResource class makes calls to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] extended dll named sqljdbc_xa.dll, which interfaces with DTC. XA calls that are received by SQLServerXAResource (XA_START, XA_END, XA_PREPARE, and so forth) are mapped to the corresponding calls to DTC functions.  
  
## See Also  
 [SQLServerXAResource Members](../../../connect/jdbc/reference/sqlserverxaresource-members.md)   
 [JDBC Driver API Reference](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
