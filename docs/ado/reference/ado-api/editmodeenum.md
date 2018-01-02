---
title: "EditModeEnum | Microsoft Docs"
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
  - "EditModeEnum"
helpviewer_keywords: 
  - "EditModeEnum enumeration [ADO]"
ms.assetid: 45d54b6e-db2c-4553-9fd0-528147d6da2f
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# EditModeEnum
Specifies the editing status of a record.  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adEditNone**|0|Indicates that no editing operation is in progress.|  
|**adEditInProgress**|1|Indicates that data in the current record has been modified but not saved.|  
|**adEditAdd**|2|Indicates that the [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md) method has been called, and the current record in the copy buffer is a new record that has not been saved in the database.|  
|**adEditDelete**|4|Indicates that the current record has been deleted.|  
  
## ADO/WFC Equivalent  
 Package: **com.ms.wfc.data**  
  
|Constant|  
|--------------|  
|AdoEnums.EditMode.NONE|  
|AdoEnums.EditMode.INPROGRESS|  
|AdoEnums.EditMode.ADD|  
|AdoEnums.EditMode.DELETE|  
  
## Applies To  
 [EditMode Property](../../../ado/reference/ado-api/editmode-property.md)
