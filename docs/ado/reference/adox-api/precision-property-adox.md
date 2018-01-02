---
title: "Precision Property (ADOX) | Microsoft Docs"
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
  - "_Column::put_Precision"
  - "_Column::PutPrecision"
  - "_Column::GetPrecision"
  - "_Column::get_Precision"
  - "_Column::Precision"
helpviewer_keywords: 
  - "Precision property [ADOX]"
ms.assetid: 0e0ecbbf-d7de-49d4-a128-5a519ecd54ba
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Precision Property (ADOX)
Indicates the maximum precision of data values in the [Column](../../../ado/reference/adox-api/column-object-adox.md).  
  
## Settings and Return Values  
 Sets and returns a **Long** value that is the maximum precision of data values in the column when the [Type](../../../ado/reference/adox-api/type-property-column-adox.md) property is a numeric type. **Precision** is ignored for all other data types.  
  
## Remarks  
 The default value is zero (**0**).  
  
 This property is read-only for [Column](../../../ado/reference/adox-api/column-object-adox.md) objects already appended to a collection.  
  
## Applies To  
 [Column Object (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## See Also  
 [ADOX Code Example: NumericScale and Precision Properties Example (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type Property (Column) (ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)   
 [Column Object (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)
