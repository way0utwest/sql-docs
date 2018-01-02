---
title: "ActualSize Property (ADO) | Microsoft Docs"
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
  - "Field20::ActualSize"
helpviewer_keywords: 
  - "ActualSize property [ADO]"
ms.assetid: 722803d0-cef5-4d4c-b79d-3f2f58052229
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ActualSize Property (ADO)
Indicates the actual length of a field???s value in bytes.  
  
## Settings and Return Values  
 Returns a **Long** value.  
  
## Remarks  
 Use the **ActualSize** property to return the actual length of a [Field](../../../ado/reference/ado-api/field-object.md) object's value. For all fields, the **ActualSize** property is read-only. If ADO cannot determine the length of the **Field** object's value, the **ActualSize** property returns **adUnknown**.  
  
 The **ActualSize** and [DefinedSize](../../../ado/reference/ado-api/definedsize-property.md) properties are different, as shown in the following example. A **Field** object with a declared type of **adVarChar** and a maximum length of 50 characters returns a **DefinedSize** property value of 50, but the **ActualSize** property value it returns is the length of the data stored in the field for the current record. **Fields** with a **DefinedSize** greater than 255 bytes are treated as variable length columns.  
  
## Applies To  
 [Field Object](../../../ado/reference/ado-api/field-object.md)  
  
## See Also  
 [ActualSize and DefinedSize Properties Example (VB)](../../../ado/reference/ado-api/actualsize-and-definedsize-properties-example-vb.md)   
 [ActualSize and DefinedSize Properties Example (VC++)](../../../ado/reference/ado-api/actualsize-and-definedsize-properties-example-vc.md)   
 [DefinedSize Property](../../../ado/reference/ado-api/definedsize-property.md)
