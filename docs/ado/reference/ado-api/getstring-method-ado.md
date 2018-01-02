---
title: "GetString Method (ADO) | Microsoft Docs"
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
apitype: "COM"
f1_keywords: 
  - "Recordset20::raw_GetString"
  - "Recordset20::GetString"
helpviewer_keywords: 
  - "GetString method [ADO]"
ms.assetid: 92452940-b2a7-456e-94fc-3780c71da33c
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "On Demand"
---
# GetString Method (ADO)
Returns the [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) as a string.  
  
## Syntax  
  
```  
  
Variant = recordset.GetString(StringFormat, NumRows, ColumnDelimiter, RowDelimiter, NullExpr)  
```  
  
## Return Value  
 Returns the **Recordset** as a string-valued **Variant** (BSTR).  
  
#### Parameters  
 *StringFormat*  
 A [StringFormatEnum](../../../ado/reference/ado-api/stringformatenum.md) value that specifies how the **Recordset** should be converted to a string. The *RowDelimiter*, *ColumnDelimiter*, and *NullExpr* parameters are used only with a *StringFormat* of **adClipString**.  
  
 *NumRows*  
 Optional. The number of rows to be converted in the **Recordset**. If *NumRows* is not specified, or if it is greater than the total number of rows in the **Recordset**, then all the rows in the **Recordset** are converted.  
  
 *ColumnDelimiter*  
 Optional. A delimiter used between columns, if specified, otherwise the TAB character.  
  
 *RowDelimiter*  
 Optional. A delimiter used between rows, if specified, otherwise the CARRIAGE RETURN character.  
  
 *NullExpr*  
 Optional. An expression used in place of a null value, if specified, otherwise the empty string.  
  
## Remarks  
 Row data, but no schema data, is saved to the string. Therefore, a **Recordset** cannot be reopened using this string.  
  
 This method is equivalent to the RDO **GetClipString** method.  
  
## Applies To  
 [Recordset Object (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## See Also  
 [GetString Method Example (VB)](../../../ado/reference/ado-api/getstring-method-example-vb.md)
