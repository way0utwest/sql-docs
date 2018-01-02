---
title: "Rowset Property (ADO) | Microsoft Docs"
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
  - "ADORecordsetConstruction::PutRowset"
  - "ADORecordsetConstruction::GetRowset"
  - "ADORecordsetConstruction::Rowset"
  - "ADORecordsetConstruction::put_Rowset"
  - "ADORecordsetConstruction::get_Rowset"
helpviewer_keywords: 
  - "Rowset property [ADO]"
ms.assetid: 7d359294-4ff2-47e0-8111-0c221b24d80e
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Rowset Property (ADO)
Gets or sets an OLE DB **Rowset** object from/on an **ADORecordsetConstruction** object. When you use put_Rowset, the rowset is turned into an ADO **Recordset** object.  
  
 Read/write.  
  
## Syntax  
  
```  
HRESULT get_Rowset([out, retval] IUnknown** ppRowset);  
HRESULT put_Rowset([in] IUnknown* pRowset);  
```  
  
## Parameters  
 *ppRowset*  
 Pointer to an OLE DB **Rowset** object.  
  
 *PRowset*  
 An OLE DB **Rowset** object.  
  
## Return Values  
 This property method returns the standard HRESULT values, including S_OK and E_FAIL.  
  
## Applies To  
 [ADORecordsetConstruction Interface](../../../ado/reference/ado-api/adorecordsetconstruction-interface.md)
