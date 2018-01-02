---
title: "GetRowsOptionEnum | Microsoft Docs"
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
  - "GetRowsOptionEnum"
helpviewer_keywords: 
  - "GetRowsOptionEnum enumeration [ADO]"
ms.assetid: adc109b9-79f4-4946-a5eb-658e22e9a8a5
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# GetRowsOptionEnum
Specifies how many records to retrieve from a [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adGetRowsRest**|-1|Retrieves the rest of the records in the **Recordset**, from either the current position or a bookmark specified by the *Start* parameter of the [GetRows](../../../ado/reference/ado-api/getrows-method-ado.md) method.|  
  
## ADO/WFC Equivalent  
 Package: **com.ms.wfc.data**  
  
|Constant|  
|--------------|  
|AdoEnums.GetRowsOption.REST|  
  
## Applies To  
 [GetRows Method (ADO)](../../../ado/reference/ado-api/getrows-method-ado.md)
