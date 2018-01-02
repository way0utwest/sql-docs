---
title: "getPacketSize Method (SQLServerDataSource) | Microsoft Docs"
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
  - "SQLServerDataSource.getPacketSize"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: b2e9f01a-2e51-47e5-90bf-43c62d1be74d
caps.latest.revision: 14
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# getPacketSize Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns the current network packet size used to communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)], specified in bytes.  
  
## Syntax  
  
```  
  
public int getPacketSize()  
```  
  
## Return Value  
 An **int** value containing the current network packet size.  
  
## Remarks  
 If the packetSize property is not set, the getPacketSize method returns the default value of 8000.  
  
## See Also  
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
