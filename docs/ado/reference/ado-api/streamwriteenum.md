---
title: "StreamWriteEnum | Microsoft Docs"
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
  - "StreamWriteEnum"
helpviewer_keywords: 
  - "StreamWriteEnum enumeration [ADO]"
ms.assetid: bdbf3405-a0bd-4f02-85d4-e3fe8da3f3f7
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# StreamWriteEnum
Specifies whether a line separator is appended to the string written to a [Stream](../../../ado/reference/ado-api/stream-object-ado.md) object.  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adWriteChar**|0|Default. Writes the specified text string (specified by the *Data* parameter) to the **Stream** object.|  
|**adWriteLine**|1|Writes a text string and a line separator character to a **Stream** object. If the [LineSeparator](../../../ado/reference/ado-api/lineseparator-property-ado.md) property is not defined, then this returns a run-time error.|  
  
## ADO/WFC Equivalent  
 These constants do not have ADO/WFC equivalents.  
  
## Applies To  
 [WriteText Method](../../../ado/reference/ado-api/writetext-method.md)
