---
title: "Interval Data Type Length | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "odbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "data types [ODBC], interval data types"
  - "length of data types [ODBC]"
  - "interval data type [ODBC], length"
ms.assetid: e9eb38d8-f9db-4401-8c62-aa394054cbbf
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Interval Data Type Length
The following rules are used to determine the length of an interval data type in characters. Length is expressed in number of characters. The number of bytes depends upon the character set. The length includes the following values added together:  
  
-   Two characters for every field in the interval that is not the leading field.  
  
-   For the leading field, the number of characters that is the express or implicit leading precision. If the leading precision is not specified, the default value is 2.  
  
-   One character for the separator between the fields.  
  
-   One plus the express or implied seconds precision. If the seconds precision is not specified, the default value is 6.  
  
 Specific column length values for each interval data type are contained in [Column Size](../../../odbc/reference/appendixes/column-size.md).
