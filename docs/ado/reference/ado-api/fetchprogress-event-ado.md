---
title: "FetchProgress Event (ADO) | Microsoft Docs"
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
  - "FetchProgress"
  - "Recordset::FetchProgress"
helpviewer_keywords: 
  - "FetchProgress event [ADO]"
ms.assetid: 301716fd-81fc-40eb-8a04-221ef7ab410e
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# FetchProgress Event (ADO)
The **FetchProgress**event is called periodically during a lengthy asynchronous operation to report how many more rows have currently been retrieved into the [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
## Syntax  
  
```  
  
FetchProgress Progress, MaxProgress, adStatus, pRecordset  
```  
  
#### Parameters  
 *Progress*  
 A **Long** value indicating the number of records that have currently been retrieved by the fetch operation.  
  
 *MaxProgress*  
 A **Long** value indicating the maximum number of records expected to be retrieved.  
  
 *adStatus*  
 An [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) status value.  
  
 *pRecordset*  
 A **Recordset** object that is the object for which the records are being retrieved.  
  
## Remarks  
 When using **FetchProgress** with a child **Recordset**, be aware that the *Progress* and *MaxProgress* parameter values are derived from the underlying [Cursor Service](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) rowset. The values returned represent the total number of records in the underlying rowset, not just the number of records in the current chapter.  
  
> [!NOTE]
>  To use **FetchProgress** with Microsoft Visual Basic, Visual Basic 6.0 or later is required.  
  
## See Also  
 [ADO Events Model Example (VC++)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [ADO Event Handler Summary](../../../ado/guide/data/ado-event-handler-summary.md)
