---
title: "getTrustStore Method (SQLServerDataSource) | Microsoft Docs"
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
  - "getTrustStore Method (SQLServerDataSource)"
apilocation: 
  - "getTrustStore Method (SQLServerDataSource)"
apitype: "Assembly"
ms.assetid: 8f5850e4-8627-49a8-ba0e-b1f4014322a5
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getTrustStore Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns the path (including file name) to the certificate trustStore file.  
  
## Syntax  
  
```  
  
public java.lang.String getTrustStore()  
```  
  
## Return Value  
 A **String** that contains the path (including file name) to the certificate trustStore file, or null if no value is set.  
  
## Remarks  
 If the trustStore property is not set, the [getTrustStore](../../../connect/jdbc/reference/gettruststore-method-sqlserverdatasource.md) method returns null.  
  
## See Also  
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
