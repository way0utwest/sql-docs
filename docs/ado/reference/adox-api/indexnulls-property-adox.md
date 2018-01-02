---
title: "IndexNulls Property (ADOX) | Microsoft Docs"
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
  - "_Index::get_IndexNulls"
  - "_Index::GetIndexNulls"
  - "_Index::put_IndexNulls"
  - "_Index::PutIndexNulls"
  - "_Index::IndexNulls"
helpviewer_keywords: 
  - "IndexNulls property [ADOX]"
ms.assetid: 313b0bf7-3f37-4823-8fca-bd9c80e078a7
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# IndexNulls Property (ADOX)
Indicates whether records that have null values in their index fields have index entries.  
  
## Settings and Return Values  
 Sets and returns an [AllowNullsEnum](../../../ado/reference/adox-api/allownullsenum.md) value. The default value is **adIndexNullsDisallow**.  
  
## Remarks  
 This property is read-only on [Index](../../../ado/reference/adox-api/index-object-adox.md) objects already appended to a collection.  
  
## Applies To  
 [Index Object (ADOX)](../../../ado/reference/adox-api/index-object-adox.md)  
  
## See Also  
 [IndexNulls Property Example (VB)](../../../ado/reference/adox-api/indexnulls-property-example-vb.md)
