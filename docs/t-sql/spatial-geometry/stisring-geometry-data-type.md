---
title: "STIsRing (geometry Data Type) | Microsoft Docs"
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
  - "STIsRing_TSQL"
  - "STIsRing (geometry Data Type)"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "STIsRing (geometry Data Type)"
ms.assetid: ea0063be-1c74-4cc4-ac6f-b65321ddfa54
caps.latest.revision: 21
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# STIsRing (geometry Data Type)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Returns 1 if a **geometry** instance fulfills the following requirements:
-   It is a **LineString** instance.  
-   It is closed.  
-   It is simple.  
-   Returns 0 if the **LineString** instance does not meet the requirements.  

 For a **geometry** instance to be closed and simple, both [STIsClosed()](../../t-sql/spatial-geometry/stisclosed-geometry-data-type.md) and [STIsSimple()](../../t-sql/spatial-geometry/stissimple-geometry-data-type.md) must return 1 when invoked on the instance. To determine the instance type of a **geometry**, use [STGeometryType()](../../t-sql/spatial-geometry/stgeometrytype-geometry-data-type.md).  
  
## Syntax  
  
```  
  
.STIsRing ( )  
```  
  
## Return Types  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] return type: **bit**  
  
 CLR return type: **SqlBoolean**  
  
## Remarks  
 This method returns null if the instance is not a **LineString**.  
  
## Examples  
 The following example creates a `LineString` instance and uses `STIsRing()` to test whether the instance is a ring.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 1 0, 0 0)', 0);  
SELECT @g.STIsRing();  
```  
  
## See Also  
 [STIsClosed &#40;geometry Data Type&#41;](../../t-sql/spatial-geometry/stisclosed-geometry-data-type.md)   
 [STGeometryType &#40;geometry Data Type&#41;](../../t-sql/spatial-geometry/stgeometrytype-geometry-data-type.md)   
 [STIsSimple &#40;geometry Data Type&#41;](../../t-sql/spatial-geometry/stissimple-geometry-data-type.md)   
 [OGC Methods on Geometry Instances](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  

