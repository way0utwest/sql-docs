---
title: "toString Method (DateTimeOffset) | Microsoft Docs"
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
ms.assetid: e77b9be3-1a02-4769-8acf-ac71d48d6a76
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# toString Method (DateTimeOffset)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Returns a string representation of the **DateTimeOffset** object.  
  
## Syntax  
  
```  
  
public String toString()  
```  
  
## Return Value  
 A string representation of the **DateTimeOffset** object.  
  
## Remarks  
 The string has the format *YYYY*-*MM*-*DD**hh*:*mm*:*ss*[.*fffffff*] [+|-]*hh*:*mm*.  
  
 The fractional seconds of the returned string are zero padded to the declared precision. For example, a **datetimeoffset(6)** with a value of "2010-03-10 12:34:56.78 -08:00" will be formatted by DateTimeOffset.toString as "2010-03-10 12:34:56.780000 -08:00".  
  
## See Also  
 [DateTimeOffset Class](../../../connect/jdbc/reference/datetimeoffset-class.md)   
 [DateTimeOffset Members](../../../connect/jdbc/reference/datetimeoffset-members.md)  
  
  
