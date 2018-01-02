---
title: "isSigned Method (SQLServerParameterMetaData) | Microsoft Docs"
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
  - "SQLServerParameterMetaData.isSigned"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: 1a4af386-e379-4a60-a107-a99e63a490ac
caps.latest.revision: 7
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# isSigned Method (SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves whether values for the designated parameter can be signed numbers.  
  
## Syntax  
  
```  
  
public boolean isSigned(int param)  
```  
  
#### Parameters  
 *param*  
  
 An **int** that indicates parameter index.  
  
## Return Value  
 **true** if the designated parameter can contain signed numbers. Otherwise, **false**.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This isSigned method is specified by the isSigned method in the java.sql.ParameterMetaData interface.  
  
## See Also  
 [SQLServerParameterMetaData Methods](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [SQLServerParameterMetaData Members](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [SQLServerParameterMetaData Class](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  
