---
title: "STMPolyFromText (geometry Data Type) | Microsoft Docs"
ms.custom: ""
ms.date: "08/03/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "t-sql|spatial-geography"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "STMPolyFromText (geometry Data Type)"
  - "STMPolyFromText_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "STMPolyFromText (geometry Data Type)"
ms.assetid: f087a61c-f063-4fb8-8f1c-251a2fed76a1
caps.latest.revision: 20
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# STMPolyFromText (geometry Data Type)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Returns a **geometry** instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation with any Z (elevation) and M (measure) values carried by the instance.
  
## Syntax  
  
```  
  
STMPolyFromText ( 'multipolygon_tagged_text' , SRID )  
```  
  
## Arguments  
 *multipolygon_tagged_text*  
 Is the WKT representation of the **geometryMultiPolygon** instance you wish to return. *multipolygon_tagged_text* is an **nvarchar(max)** expression.  
  
 *SRID*  
 Is an **int** expression representing the spatial reference ID (SRID) of the **geometryMultiPolygon** instance you wish to return.  
  
## Return Types  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] return type: **geometry**  
  
 CLR return type: **Sql Geometry**  
  
 OGC type: **MultiPolygon**  
  
## Remarks  
 This method will throw a **FormatException** if the input is not well-formatted.  
  
## Examples  
 The following example uses `STMPolyFromText()` to create a `geometry` instance.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPolyFromText('MULTIPOLYGON (((5 5, 10 5, 10 10, 5 5)), ((10 10, 100 10, 200 200, 30 30, 10 10)))', 0);  
SELECT @g.ToString();  
```  
  
## See Also  
 [OGC Static Geometry Methods](../../t-sql/spatial-geometry/ogc-static-geometry-methods.md)  
  
  

