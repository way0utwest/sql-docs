---
title: "Collections (ADO - WFC Syntax) | Microsoft Docs"
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
  - "syntax indexes [ADO], ADO/WFC"
  - "collections [ADO], ADO/WFC syntax"
  - "ADO/WFC syntax index [ADO]"
ms.assetid: 073f9a0e-c755-42dd-9f71-4647d68e331a
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Collections (ADO - WFC Syntax)
**package com.ms.wfc.data**  
  
## Parameters  
  
### Methods  
  
```  
public void append(com.ms.wfc.data.Parameter param)  
public void delete(int n)  
public void delete(String s)  
public void refresh()  
public Parameter getItem(int n)  
public Parameter getItem(String s)  
```  
  
### Properties  
  
```  
public int getCount()  
```  
  
## Fields  
  
### Methods  
  
```  
public void append(String name, int type)  
public void append(String name, int type, int definedSize)  
public void append(String name, int type, int definedSize, int attrib)  
public void delete(int n)  
public void delete(String s)  
public void refresh()  
public com.ms.wfc.data.Field getItem(int n)  
public com.ms.wfc.data.Field getItem(String s)  
```  
  
### Properties  
  
```  
public int getCount()  
```  
  
## Errors  
  
### Methods  
  
```  
public void clear()  
public void refresh()  
public com.ms.wfc.data.Error getItem(int n)  
public com.ms.wfc.data.Error getItem(String s)  
```  
  
### Properties  
  
```  
public int getCount()  
```  
  
## See Also  
 [Errors Collection (ADO)](../../../ado/reference/ado-api/errors-collection-ado.md)   
 [Fields Collection (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)   
 [Parameters Collection (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)
