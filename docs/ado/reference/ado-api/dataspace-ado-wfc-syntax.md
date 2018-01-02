---
title: "DataSpace (ADO - WFC Syntax) | Microsoft Docs"
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
helpviewer_keywords: 
  - "DataSpace collection [ADO], ADO/WFC syntax"
ms.assetid: 950d45d8-07de-467b-b255-f9a7b997204c
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# DataSpace (ADO - WFC Syntax)
The **createObject** method of the **DataSpace** class specifies both a business object to process client application requests (*progid*) and the communications protocol and server (*connection*). **createObject** returns an [ObjectProxy](../../../ado/reference/ado-api/objectproxy-ado-wfc-syntax.md) object that represents the server.  
  
## package com.ms.wfc.data  
  
### Constructor  
  
```  
public DataSpace()  
```  
  
### Methods  
  
```  
public static ObjectProxy DataSpace.createObject(String  
    progid, String connection)  
```  
  
### Properties  
  
```  
public static int getInternetTimeout()  
public static void setInternetTimeout(int plInetTimeout)  
```  
  
## See Also  
 [DataSpace Object (RDS)](../../../ado/reference/rds-api/dataspace-object-rds.md)
