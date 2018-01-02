---
title: "Count (Hierarchy Levels) (MDX) | Microsoft Docs"
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
f1_keywords: 
  - "COUNT"
dev_langs: 
  - "kbMDX"
helpviewer_keywords: 
  - "Count function [MDX]"
ms.assetid: 3de6a824-2ff3-47ac-9ceb-e3369a04f35d
caps.latest.revision: 33
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
ms.workload: "Inactive"
---
# Count (Hierarchy Levels) (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Returns the number of levels in hierarchy.  
  
## Syntax  
  
```  
  
Hierarchy_Expression.Levels.Count  
```  
  
## Arguments  
 *Hierarchy_Expression*  
 A valid Multidimensional Expressions (MDX) expression that returns a hierarchy.  
  
## Remarks  
 Returns the number of levels in a hierarchy, including the `[All]` level, if applicable.  
  
> [!IMPORTANT]  
>  When a dimension contains only a single visible hierarchy, the hierarchy can be referred to either by the dimension name or by the hierarchy name, because the dimension name is resolved to its only visible hierarchy. For example, `Measures.Levels.Count` is a valid MDX expression because it resolves to the only hierarchy in the Measures dimension.  
  
## Example  
 The following example returns a count of the number of levels in the Product Categories user-defined hierarchy in the Adventure Works cube.  
  
```  
WITH MEMBER measures.X AS  
   [Product].[Product Categories].Levels.Count   
Select Measures.X ON 0  
FROM [Adventure Works]  
```  
  
## See Also  
 [Count &#40;Dimension&#41; &#40;MDX&#41;](../mdx/count-dimension-mdx.md)   
 [Count &#40;Tuple&#41; &#40;MDX&#41;](../mdx/count-tuple-mdx.md)   
 [Count &#40;Set&#41; &#40;MDX&#41;](../mdx/count-set-mdx.md)   
 [MDX Function Reference &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
