---
title: "execute Method (java.lang.String, int[]) | Microsoft Docs"
ms.custom: ""
ms.date: "02/07/2017"
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
  - "SQLServerStatement.execute (javal.lang.String.int[])"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: dc73d1c3-e756-43af-b1fc-ac438cbd0965
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# execute Method (java.lang.String, int[])

  Runs the given SQL statement, which can return multiple results, and signals [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion-md.md)] that the auto-generated keys that are indicated in the given array should be made available for retrieval.

## Syntax

```Java
public final boolean execute(
	java.lang.String sql,
	int[] columnIndexes)
```

#### Parameters
*sql*

A **String** that contains an SQL statement.

*columnIndexes*

An array of **int**s that indicates the column indexes of the auto-generated keys that should be made available.

## Return Value
**true** if the first result is a result set. Otherwise, **false**.
  
## Exceptions
[SQLServerException](./sqlserverexception-class.md)

## Remarks
This execute method is specified by the execute method in the java.sql.Statement interface.

## See Also

[execute Method &#40;SQLServerStatement&#41;](./execute-method-sqlserverstatement.md)

[SQLServerStatement members](./sqlserverstatement-members.md)

[SQLServerStatement class](./sqlserverstatement-class.md)
