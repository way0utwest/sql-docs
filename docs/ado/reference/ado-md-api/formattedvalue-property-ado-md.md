---
title: "FormattedValue Property (ADO MD) | Microsoft Docs"
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
  - "Cell::FormattedValue"
  - "FormattedValue"
helpviewer_keywords: 
  - "FormattedValue property [ADO MD]"
ms.assetid: 5c06451e-06ec-4da6-9a87-2d043469248a
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# FormattedValue Property (ADO MD)
Indicates the formatted display of a [cell](../../../ado/reference/ado-md-api/cell-object-ado-md.md) value.  
  
## Return Values  
 Returns a **String** and is read-only.  
  
## Remarks  
 Use the **FormattedValue** property to obtain the formatted display value of the [Value](../../../ado/reference/ado-md-api/value-property-ado-md.md) property of a [Cell](../../../ado/reference/ado-md-api/cell-object-ado-md.md) object. For example, if the value of a cell was 1056.87, and this value represented a dollar amount, **FormattedValue** would be $1,056.87.  
  
## Applies To  
 [Cell Object (ADO MD)](../../../ado/reference/ado-md-api/cell-object-ado-md.md)  
  
## See Also  
 [Cellset Example (VB)](../../../ado/reference/ado-md-api/cellset-example-vb.md)   
 [Value Property (ADO MD)](../../../ado/reference/ado-md-api/value-property-ado-md.md)
