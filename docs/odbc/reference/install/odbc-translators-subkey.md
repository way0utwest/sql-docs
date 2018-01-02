---
title: "ODBC Translators Subkey | Microsoft Docs"
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
  - "translator subkey [ODBC]"
  - "subkeys [ODBC], translator subkey"
  - "registry entries for components [ODBC], translator subkey"
ms.assetid: 6b170f1f-e263-4aac-9d49-8d0ca0470ca2
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ODBC Translators Subkey
The values under the ODBC Translators subkey list the installed translators. The format of these values is shown in the following table.  
  
|Name|Data type|Data|  
|----------|---------------|----------|  
|*translator-desc*|REG_SZ|**Installed**|  
  
 The *translator-desc* name is defined by the translator developer.  
  
 For example, suppose a user has installed the Microsoft® Code Page Translator and a custom ASCII to EBCDIC translator. The values under the ODBC Translators subkey might be as follows:  
  
```  
MS Code Page Translator: REG_SZ : Installed  
ASCII to EBCDIC: REG_SZ : Installed.  
```
