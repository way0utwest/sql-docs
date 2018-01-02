---
title: "Operation of Non-Parameterized Commands | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "ado"
ms.technology:
  - "drivers"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "non-parameterized commands [ADO]"
  - "data shaping [ADO], non-parameterized commands"
ms.assetid: 9700e50a-9f17-4ba3-8afb-f750741dc6ca
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Operation of Non-Parameterized Commands
For non-parameterized commands, all the provider commands are executed and the **Recordsets** are created during command execution. If the command is executed synchronously, all the **Recordsets** will be fully populated. If an asynchronous population mode was selected, the populated state of the **Recordsets** will depend on the population mode and the size of the **Recordsets**.  
  
 For example, the *parent-command* could return a **Recordset** of customers for a company from a Customers table, and the *child-command* could return a **Recordset** of orders for all customers from an Orders table.  
  
```  
SHAPE {SELECT * FROM Customers}   
   APPEND ({SELECT * FROM Orders} AS chapOrders   
   RELATE customerID TO customerID)  
```  
  
 For non-parameterized parent-child relationships, each parent and child **Recordset** object must have a column in common to associate them. The columns are named in the RELATE clause, *parent-column* first and then *child-column*. The columns may have different names in their respective **Recordset** objects but must refer to the same information in order to specify a meaningful relation. For example, the **Customers** and **Orders Recordset** objects could both have a customerID field. Because the membership of the child **Recordset** is determined by the provider command, the child **Recordset** can contain orphaned rows. These orphaned rows are inaccessible without additional reshaping.  
  
 Data shaping appends a chapter column to the parent **Recordset**. The values in the chapter column are references to rows in the child **Recordset**, which satisfy the RELATE clause. That is, the same value is in the *parent-column* of a given parent row as is in the *child-column* of all the rows of the chapter child. When multiple TO clauses are used in the same RELATE clause, they are implicitly combined using an AND operator. If the parent columns in the RELATE clause do not constitute a key to the parent **Recordset**, a single child row can have multiple parent rows.  
  
 When you access the reference in the chapter column, ADO automatically retrieves the **Recordset** represented by the reference. Note that in a non-parameterized command, although the entire child **Recordset** has been retrieved, the chapter only presents a subset of rows.  
  
 If the appended column has no *chapter-alias*, a name will be generated for it automatically. A [Field](../../../ado/reference/ado-api/field-object.md) object for the column will be appended to the **Recordset** object's [Fields](../../../ado/reference/ado-api/fields-collection-ado.md) collection, and its data type will be **adChapter**.  
  
 For information about navigating a hierarchical **Recordset**, see [Accessing Rows in a Hierarchical Recordset](../../../ado/guide/data/accessing-rows-in-a-hierarchical-recordset.md).  
  
## See Also  
 [Data Shaping Example](../../../ado/guide/data/data-shaping-example.md)   
 [Formal Shape Grammar](../../../ado/guide/data/formal-shape-grammar.md)   
 [Shape Commands in General](../../../ado/guide/data/shape-commands-in-general.md)
