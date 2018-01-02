---
title: "Cousin (MDX) | Microsoft Docs"
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
  - "COUSIN"
dev_langs: 
  - "kbMDX"
helpviewer_keywords: 
  - "Cousin function"
ms.assetid: 9a416685-d35d-4d9c-a9f6-4574cbe59aea
caps.latest.revision: 33
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
ms.workload: "Inactive"
---
# Cousin (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Returns the child member with the same relative position under a parent member as the specified child member.  
  
## Syntax  
  
```  
  
Cousin( Member_Expression , Ancestor_Member_Expression )  
```  
  
## Arguments  
 *Member_Expression*  
 A valid Multidimensional Expressions (MDX) expression that returns a member.  
  
 *Ancestor_Member_Expression*  
 A valid Multidimensional Expressions (MDX) member expression that returns an ancestor member.  
  
## Remarks  
 This function operates on the order and position of members within levels. If two hierarchies exist, in which the first one has four levels and the second one has five levels, the cousin of the third level of the first hierarchy is the third level of the second hierarchy.  
  
## Examples  
 The following example retrieves the cousin of the fourth quarter of fiscal year 2002, based on its ancestor at the year level in fiscal year 2003. The retrieved cousin is the fourth quarter of fiscal year 2003.  
  
```  
SELECT Cousin   
   ( [Date].[Fiscal].[Fiscal Quarter].[Q4 FY 2002],  
     [Date].[Fiscal].[FY 2003]  
   ) ON 0  
FROM [Adventure Works]  
```  
  
 The following example retrieves the cousin of the month of July of fiscal year 2002 based on its ancestor at the quarter level in the second quarter of fiscal year 2004. The retrieved cousin is the month of October of 2003.  
  
```  
SELECT Cousin   
   ([Date].[Fiscal].[Month].[July 2002] ,  
    [Date].[Fiscal].[Fiscal Quarter].[Q2 FY 2004]  
   ) ON 0  
FROM [Adventure Works]  
```  
  
## See Also  
 [MDX Function Reference &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
