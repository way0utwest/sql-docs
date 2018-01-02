---
title: "LineSeparator Property (ADO) | Microsoft Docs"
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
  - "_Stream::LineSeparator"
helpviewer_keywords: 
  - "LineSeparator property [ADO]"
ms.assetid: 0b20fbb8-6b83-48ec-b442-f96c8a4bafbb
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# LineSeparator Property (ADO)
Indicates the binary character to be used as the line separator in text [Stream](../../../ado/reference/ado-api/stream-object-ado.md) objects.  
  
## Settings and Return Values  
 Sets or returns a [LineSeparatorsEnum](../../../ado/reference/ado-api/lineseparatorsenum.md) value that indicates the line separator character used in the **Stream**. The default value is **adCRLF**.  
  
## Remarks  
 **LineSeparator** is used to interpret lines when reading the content of a text **Stream**. Lines can be skipped with the [SkipLine](../../../ado/reference/ado-api/skipline-method.md) method.  
  
 **LineSeparator** is used only with text **Stream** objects ([Type](../../../ado/reference/ado-api/type-property-ado-stream.md) is **adTypeText**). This property is ignored if **Type** is **adTypeBinary**.  
  
## Applies To  
 [Stream Object (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## See Also  
 [Stream Object (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
