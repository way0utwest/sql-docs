---
title: "Recordset Dynamic Properties in XML | Microsoft Docs"
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
  - "Recordset dynamic properties in XML [ADO]"
ms.assetid: 52f8e379-812a-4db8-9210-94458926301c
caps.latest.revision: 3
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Recordset Dynamic Properties in XML
The following Recordset provider-specific properties (from the Client Cursor Engine) are currently persisted into the XML format:  
  
-   Update Resync  
  
-   Unique Table  
  
-   Unique Schema  
  
-   Unique Catalog  
  
-   Resync Command  
  
-   IRowsetChange  
  
-   IRowsetUpdate  
  
-   CommandTimeout  
  
-   BatchSize  
  
-   UpdateCriteria  
  
-   Reshape Name  
  
-   AutoRecalc  
  
 These properties are saved in the schema section as attributes of the element definition for the Recordset being persisted. These attributes are defined in the rowset schema namespace and must have the prefix "rs:".  
  
## See Also  
 [Persisting Records in XML Format](../../../ado/guide/data/persisting-records-in-xml-format.md)
