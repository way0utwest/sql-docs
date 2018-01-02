---
title: "Stream Property | Microsoft Docs"
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
  - "ADOStreamConstruction::GetStream"
  - "ADOStreamConstruction::PutStream"
  - "ADOStreamConstruction::put_Stream"
  - "ADOStreamConstruction::Stream"
  - "ADOStreamConstruction::get_Stream"
helpviewer_keywords: 
  - "Stream property"
ms.assetid: 4a44f9f6-0265-4c00-8def-d85b6af923b1
caps.latest.revision: 6
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Stream Property
Gets or sets an OLE DB **Stream** object from/on an **ADOStreamConstruction** object.  
  
 Read/write.  
  
## Syntax  
  
```  
HRESULT get_Stream([out, retval] IUnknown** ppStream);  
HRESULT put_Stream([in] IUnknown* pStream);  
```  
  
## Parameters  
 *ppStream*  
 Pointer to an OLE DB **Stream** object.  
  
 *pStream*  
 An OLE DB **Stream** object.  
  
## Return Values  
 This property method returns the standard HRESULT values. This includes S_OK and E_FAIL.  
  
## Applies To  
 [ADOStreamConstruction Interface](../../../ado/reference/ado-api/adostreamconstruction-interface.md)
