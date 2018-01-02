---
title: "Attributes Property (ADOX) | Microsoft Docs"
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
  - "_Column::put_Attributes"
  - "_Column::Attributes"
  - "_Column::PutAttributes"
  - "_Column::get_Attributes"
  - "_Column::GetAttributes"
helpviewer_keywords: 
  - "Attributes property [ADOX]"
ms.assetid: e3abb359-79a3-4c22-b3a8-2900817e0d23
caps.latest.revision: 15
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Attributes Property (ADOX)
Describes column characteristics.  
  
## Settings and Return Values  
 Sets or returns a **Long** value. The value specifies characteristics of the table that is represented by the [Column](../../../ado/reference/adox-api/column-object-adox.md) object. The value can be a combination of [ColumnAttributesEnum](../../../ado/reference/adox-api/columnattributesenum.md) constants. The default value is zero (**0**), which is neither **adColFixed** nor **adColNullable**.  
  
## Applies To  
  
- [Column Object (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## See Also  
 [Attributes Property Example (VB)](../../../ado/reference/adox-api/attributes-property-example-vb.md)
