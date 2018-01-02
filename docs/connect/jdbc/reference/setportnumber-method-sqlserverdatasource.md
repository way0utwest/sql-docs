---
title: "setPortNumber Method (SQLServerDataSource) | Microsoft Docs"
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
  - "SQLServerDataSource.setPortNumber"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 59c5fa23-bc1a-4142-af17-70e275f0b833
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# setPortNumber Method (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Sets the port number to be used to communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)].  
  
## Syntax  
  
```  
  
public void setPortNumber(int portNumber)  
```  
  
#### Parameters  
 *portNumber*  
  
 An **int** value that contains the port number.  
  
## Remarks  
 The port number is the TCP/IP port number that is used when opening a socket connection to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]. If the portNumber property is not set, the [getPortNumber](../../../connect/jdbc/reference/getportnumber-method-sqlserverdatasource.md) method returns the default value of 1433.  
  
> [!NOTE]  
>  The setPortNumber method does not do any range checking on the port value passed in. You can pass a port number that is not valid, like 99999, without triggering an error.  
  
## See Also  
 [SQLServerDataSource Members](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource Class](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
