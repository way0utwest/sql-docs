---
title: "AllowNullsEnum | Microsoft Docs"
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
  - "AllowNullsEnum"
helpviewer_keywords: 
  - "AllowNullsEnum enumeration [ADOX]"
ms.assetid: 6acf3689-1a7f-4379-9d7f-df452ccbac27
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# AllowNullsEnum
Specifies whether records with null values are indexed.  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adIndexNullsAllow**|0|The index does allow entries in which the key columns are null. If a null value is entered in a key column, the entry is inserted into the index.|  
|**adIndexNullsDisallow**|1|Default. The index does not allow entries in which the key columns are null. If a null value is entered in a key column, an error will occur.|  
|**adIndexNullsIgnore**|2|The index does not insert entries containing null keys. If a null value is entered in a key column, the entry is ignored and no error occurs.|  
|**adIndexNullsIgnoreAny**|4|The index does not insert entries where some key column has a null value. For an index having a multi-column key, if a null value is entered in some column, the entry is ignored and no error occurs.|  
  
## Applies To  
 [IndexNulls Property (ADOX)](../../../ado/reference/adox-api/indexnulls-property-adox.md)
