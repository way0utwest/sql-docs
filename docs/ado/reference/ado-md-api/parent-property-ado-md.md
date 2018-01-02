---
title: "Parent Property (ADO MD) | Microsoft Docs"
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
  - "Parent"
  - "Member::Parent"
helpviewer_keywords: 
  - "Parent property [ADO MD]"
ms.assetid: 32c278c1-d8e1-4bb7-9ecd-2fbfdffee34b
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Parent Property (ADO MD)
Indicates the member that is the parent of the current [member](../../../ado/reference/ado-md-api/member-object-ado-md.md) in a hierarchy.  
  
## Return Values  
 Returns a [Member](../../../ado/reference/ado-md-api/member-object-ado-md.md) object and is read-only.  
  
## Remarks  
 A member that is at the top level of a hierarchy (the root) has no parent. This property is supported only on **Member** objects belonging to a [Level](../../../ado/reference/ado-md-api/level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](../../../ado/reference/ado-md-api/position-object-ado-md.md) object.  
  
## Applies To  
 [Member Object (ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)  
  
## See Also  
 [Children Property (ADO MD)](../../../ado/reference/ado-md-api/children-property-ado-md.md)
