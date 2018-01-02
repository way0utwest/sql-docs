---
title: "Error (MDX) | Microsoft Docs"
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
  - "ERROR"
dev_langs: 
  - "kbMDX"
helpviewer_keywords: 
  - "Error function"
ms.assetid: 2caac19b-b297-443e-9299-648ef88a5039
caps.latest.revision: 32
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
ms.workload: "Inactive"
---
# Error (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Raises an error, optionally providing a specified error message.  
  
## Syntax  
  
```  
  
Error( [ Error_Text ] )  
```  
  
## Arguments  
 *Error_Text*  
 A valid string expression containing the error message to be returned.  
  
## Examples  
 The following query shows how to use the **Error** function inside a calculated measure:  
  
 `WITH MEMBER MEASURES.ERRORDEMO AS ERROR("THIS IS AN ERROR")`  
  
 `SELECT`  
  
 `MEASURES.ERRORDEMO ON 0`  
  
 `FROM [Adventure Works]`  
  
## See Also  
 [MDX Function Reference &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
