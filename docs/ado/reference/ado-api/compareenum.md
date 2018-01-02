---
title: "CompareEnum | Microsoft Docs"
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
  - "CompareEnum"
helpviewer_keywords: 
  - "CompareEnum enumeration [ADO]"
ms.assetid: bc8f710d-0621-4673-8d8e-0361e44abed0
caps.latest.revision: 11
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# CompareEnum
Specifies the relative position of two records represented by their bookmarks.  
  
|Constant|Value|Description|  
|--------------|-----------|-----------------|  
|**adCompareEqual**|1|Indicates that the bookmarks are equal.|  
|**adCompareGreaterThan**|2|Indicates that the first bookmark is after the second.|  
|**adCompareLessThan**|0|Indicates that the first bookmark is before the second.|  
|**adCompareNotComparable**|4|Indicates that the bookmarks cannot be compared.|  
|**adCompareNotEqual**|3|Indicates that the bookmarks are not equal and not ordered.|  
  
## ADO/WFC Equivalent  
 Package: **com.ms.wfc.data**  
  
|Constant|  
|--------------|  
|AdoEnums.Compare.EQUAL|  
|AdoEnums.Compare.GREATERTHAN|  
|AdoEnums.Compare.LESSTHAN|  
|AdoEnums.Compare.NOTCOMPARABLE|  
|AdoEnums.Compare.NOTEQUAL|  
  
## Applies To  
 [CompareBookmarks Method (ADO)](../../../ado/reference/ado-api/comparebookmarks-method-ado.md)  
  
## See Also  
 [CompareBookmarks Method (ADO)](../../../ado/reference/ado-api/comparebookmarks-method-ado.md)
