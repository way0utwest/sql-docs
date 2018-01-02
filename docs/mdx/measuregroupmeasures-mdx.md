---
title: "MeasureGroupMeasures (MDX) | Microsoft Docs"
ms.custom: ""
ms.date: "03/02/2016"
ms.prod: "analysis-services"
ms.prod_service: "analysis-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "kbMDX"
helpviewer_keywords: 
  - "MeasureGroupMeasures function"
ms.assetid: 69d9b205-1ca7-4741-9ca9-c7926bc87ead
caps.latest.revision: 14
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
ms.workload: "Inactive"
---
# MeasureGroupMeasures (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Returns a set of measures that belongs to the specified measure group.  
  
## Syntax  
  
```  
  
MEASUREGROUPMEASURES(MeasureGroupName)  
```  
  
## Arguments  
 *MeasureGroupName*  
 A valid string expression that contains the name of the measure group from which to retrieve the set of measures.  
  
## Remarks  
 The specified string must match the measure group name exactly. Square brackets for measure group names with spaces are not required.  
  
## Example  
 The following example returns all of the measures in the Internet Sales measure group in the Adventure Works cube.  
  
```  
SELECT MeasureGroupMeasures('Internet Sales') ON 0  
FROM [Adventure Works]  
```  
  
## See Also  
 [MDX Function Reference &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
