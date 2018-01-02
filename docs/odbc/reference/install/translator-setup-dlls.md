---
title: "Translator Setup DLLs | Microsoft Docs"
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
  - "translator setup DLL [ODBC]"
ms.assetid: b3ca79e9-01b9-4541-81de-bbbad24ca736
caps.latest.revision: 8
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Translator Setup DLLs
> [!NOTE]  
>  Starting with Windows XP and Windows Server 2003, ODBC is included in the Windows operation system. You should only explicitly install ODBC on earlier versions of Windows.  
  
 The translator setup DLL contains the **ConfigTranslator** function, which returns the default option for a translator. If necessary, it prompts the user for this information. For a complete description of this function, see [Setup DLL API Reference](../../../odbc/reference/syntax/setup-dll-api-reference.md).  
  
 The translator setup DLL is written by the translator developer. It can be part of the translator DLL or a separate DLL.
