---
title: "ConnectOptionEnum | Microsoft Docs"
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
  - "ConnectOptionEnum"
helpviewer_keywords: 
  - "ConnectOptionEnum enumeration [ADO]"
ms.assetid: bff07eeb-dee3-4e4e-9b2d-d56061ea744d
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ConnectOptionEnum
Specifies whether the [Open](../../../ado/reference/ado-api/open-method-ado-connection.md) method of a [Connection](../../../ado/reference/ado-api/connection-object-ado.md) object should return after the connection is established (synchronously) or before (asynchronously).  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adAsyncConnect**|16|Opens the connection asynchronously. The [ConnectComplete](../../../ado/reference/ado-api/connectcomplete-and-disconnect-events-ado.md) event may be used to determine when the connection is available.|  
|**adConnectUnspecified**|-1|Default. Opens the connection synchronously.|  
  
## ADO/WFC Equivalent  
 Package: **com.ms.wfc.data**  
  
|Constant|  
|--------------|  
|AdoEnums.ConnectOption.ASYNCCONNECT|  
|AdoEnums.ConnectOption.CONNECTUNSPECIFIED|  
  
## Applies To  
 [Open Method (ADO Connection)](../../../ado/reference/ado-api/open-method-ado-connection.md)
