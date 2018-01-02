---
title: "valueOf Method (java.sql.Timestamp, java.util.Calendar) | Microsoft Docs"
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
ms.assetid: 7320c383-0b06-446d-963b-7005e50324a2
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# valueOf Method (java.sql.Timestamp, java.util.Calendar)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Creates a **DateTimeOffset** object representing a point in time at a particular offset from GMT given a java.sql.Timestamp value and a java.util.Calendar value indicating the offset.  
  
## Syntax  
  
```  
  
public static DateTimeOffset valueOf(java.sql.Timestamp timestamp, java.util.Calendar calendar)  
```  
  
#### Parameters  
 *timestamp*  
  
 Ajava.sql.Timestamp value.  
  
 *calendar*  
  
 The offset value.  The date and time components of *calendar* will be set according to the *timestamp* value.  
  
## Return Value  
 Returns a DateTimeOffset object representing the point in time given by the java.sql.Timestamp object at the given java.util.Calendar object’s time zone.  
  
## Remarks  
 This method also sets the java.util.Calendar object to the point in time given by the java.sql.Timestamp object.  
  
## See Also  
 [DateTimeOffset Class](../../../connect/jdbc/reference/datetimeoffset-class.md)   
 [DateTimeOffset Members](../../../connect/jdbc/reference/datetimeoffset-members.md)  
  
  
