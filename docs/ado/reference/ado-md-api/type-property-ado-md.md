---
title: "Type Property (ADO MD) | Microsoft Docs"
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
  - "Member::Type"
  - "Type"
helpviewer_keywords: 
  - "Type property [ADO MD]"
ms.assetid: 34698910-64b9-41d8-8531-9de12f2b1e32
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Type Property (ADO MD)
Indicates the type of the current [member](../../../ado/reference/ado-md-api/member-object-ado-md.md).  
  
## Return Values  
 Returns a [MemberTypeEnum](../../../ado/reference/ado-md-api/membertypeenum.md) value and is read-only.  
  
## Remarks  
 This property is supported only on [Member](../../../ado/reference/ado-md-api/member-object-ado-md.md) objects belonging to a [Level](../../../ado/reference/ado-md-api/level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](../../../ado/reference/ado-md-api/position-object-ado-md.md) object.  
  
## Applies To  
 [Member Object (ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)
