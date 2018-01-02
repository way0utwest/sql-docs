---
title: "Parameter Data Types | Microsoft Docs"
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
  - "data types [ODBC], parameters"
  - "parameter data type [ODBC]"
  - "minimum SQL syntax supported [ODBC]"
  - "ODBC drivers [ODBC], minimum SQL syntax supported"
ms.assetid: fd7e99d8-d26a-408c-9733-6ffccde99f75
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Parameter Data Types
Even though each parameter specified with **SQLBindParameter** is defined using an SQL data type, the parameters in an SQL statement have no intrinsic data type. Therefore, parameter markers can be included in an SQL statement only if their data types can be inferred from another operand in the statement. For example, in an arithmetic expression such as ? + COLUMN1, the data type of the parameter can be inferred from the data type of the named column represented by COLUMN1. An application cannot use a parameter marker if the data type cannot be determined.  
  
 The following table describes how a data type is determined for several types of parameters, in accordance with SQL-92. For a more comprehensive specification on inferring the parameter type when other SQL clauses are used, see the SQL-92 specification.  
  
|Location of parameter|Assumed data type|  
|---------------------------|-----------------------|  
|One operand of a binary arithmetic or comparison operator|Same as the other operand|  
|The first operand in a **BETWEEN** clause|Same as the second operand|  
|The second or third operand in a **BETWEEN** clause|Same as the first operand|  
|An expression used with **IN**|Same as the first value or the result column of the subquery|  
|A value used with **IN**|Same as the expression or the first value if there is a parameter marker in the expression|  
|A pattern value used with **LIKE**|VARCHAR|  
|An update value used with **UPDATE**|Same as the update column|
