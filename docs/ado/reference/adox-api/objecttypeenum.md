---
title: "ObjectTypeEnum | Microsoft Docs"
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
  - "ObjectTypeEnum"
helpviewer_keywords: 
  - "ObjectTypeEnum enumeration [ADOX]"
ms.assetid: 3fdecfca-aa91-4596-ad98-610f1b7f840b
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ObjectTypeEnum
Specifies the type of database object for which to set permissions or ownership.  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adPermObjColumn**|2|The object is a column.|  
|**adPermObjDatabase**|3|The object is a database.|  
|**adPermObjProcedure**|4|The object is a procedure.|  
|**adPermObjProviderSpecific**|-1|The object is a type defined by the provider. An error will occur if the *ObjectType* parameter is **adPermObjProviderSpecific** and an *ObjectTypeId* is not supplied.|  
|**adPermObjTable**|1|The object is a table.|  
|**adPermObjView**|5|The object is a view.|  
  
## Applies To  
  
|||  
|-|-|  
|[GetObjectOwner Method (ADOX)](../../../ado/reference/adox-api/getobjectowner-method-adox.md)|[GetPermissions Method (ADOX)](../../../ado/reference/adox-api/getpermissions-method-adox.md)|  
|[SetObjectOwner Method](../../../ado/reference/adox-api/setobjectowner-method.md)|[SetPermissions Method (ADOX)](../../../ado/reference/adox-api/setpermissions-method-adox.md)|
