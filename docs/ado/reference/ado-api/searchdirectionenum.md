---
title: "SearchDirectionEnum | Microsoft Docs"
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
  - "SearchDirectionEnum"
helpviewer_keywords: 
  - "SearchDirectionEnum enumeration [ADO]"
ms.assetid: 81272ae3-2165-4f4e-adfe-9ede0368cb17
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SearchDirectionEnum
Specifies the direction of a record search within a [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adSearchBackward**|-1|Searches backward, stopping at the beginning of the **Recordset**. If a match is not found, the record pointer is positioned at [BOF](../../../ado/reference/ado-api/bof-eof-properties-ado.md).|  
|**adSearchForward**|1|Searches forward, stopping at the end of the **Recordset**. If a match is not found, the record pointer is positioned at [EOF](../../../ado/reference/ado-api/bof-eof-properties-ado.md).|  
  
## ADO/WFC Equivalent  
 Package: **com.ms.wfc.data**  
  
|Constant|  
|--------------|  
|AdoEnums.SearchDirection.BACKWARD|  
|AdoEnums.SearchDirection.FORWARD|  
  
## Applies To  
 [Find Method (ADO)](../../../ado/reference/ado-api/find-method-ado.md)
