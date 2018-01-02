---
title: "Visual FoxPro Field Data Types | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "odbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "field data types [ODBC]"
  - "Visual FoxPro ODBC driver [ODBC], data types"
ms.assetid: 50b733dc-679a-4b10-bc5d-98bb474dead2
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Visual FoxPro Field Data Types
The following table lists the values for the *FieldType* argument in ALTER TABLE and CREATE TABLE and indicates whether *nFieldWidth* and *nPrecision* arguments are required.  
  
|*FieldType*|*NFieldWidth*|*nPrecision*|Description|  
|-----------------|-------------------|------------------|-----------------|  
|B|-|d|Double|  
|C|N|-|Character field of width *n*|  
|D|-|-|Date|  
|F|N|d|Floating numeric field of width *n* with *d* decimal places|  
|G|-|-|General|  
|I|-|-|Integer|  
|L|-|-|Logical|  
|M|-|-|Memo|  
|N|N|d|Numeric field of width *n* with *d* decimal places|  
|T|-|-|DateTime|  
|Y|-|-|Currency|
