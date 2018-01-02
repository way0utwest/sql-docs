---
title: "Namespaces | Microsoft Docs"
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
helpviewer_keywords: 
  - "namespaces in ADO"
ms.assetid: efff5569-db52-451d-a039-2e74870534da
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Namespaces
The XML persistence format in ADO uses the following four namespaces.  
  
## Remarks  
 The XML persistence format in ADO uses the following four namespaces.  
  
|Prefix|Description|  
|------------|-----------------|  
|s|Refers to the "XML-Data" namespace containing the elements and attributes that define the schema of the current Recordset.|  
|dt|Refers to the data type definitions specification.|  
|rs|Refers to the namespace containing elements and attributes specific to ADO Recordset properties and attributes.|  
|z|Refers to the schema of the current rowset.|  
  
 A client should not add its own tags to these namespaces, as defined by the specification. For example, a client should not define a namespace as "urn:schemas-microsoft-com:rowset" and then write out something such as "rs:MyOwnTag." To learn more about namespaces, see the [W3C Namespaces in XML Recommendation](http://www.w3.org/TR/REC-xml-names/).  
  
> [!IMPORTANT]
>  The ID for the schema tag must be "RowsetSchema," and the namespace used to refer to the schema of the current rowset must point to "#RowsetSchema."  
  
 Note that the prefix of the namespace — the part between the colon and the equal sign — is arbitrary.  
  
```  
xmlns:rs="urn:schemas-microsoft-com:rowset"  
```  
  
 The user can define this to be any name as long as this name is consistently used throughout the XML document. ADO always writes out "s," "rs," "dt," and "z," but these prefix names are not hard-coded into the loading component.  
  
## See Also  
 [Persisting Records in XML Format](../../../ado/guide/data/persisting-records-in-xml-format.md)
