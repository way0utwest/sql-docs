---
title: "Cursor and Lock Characteristics | Microsoft Docs"
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
helpviewer_keywords: 
  - "locks [ADO], characteristics"
  - "adOpenDynamic [ADO]"
  - "cursors [ADO], characteristics"
ms.assetid: 459c29cb-4230-42bf-8cc2-f3132ccc7aba
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Cursor and Lock Characteristics
While the characteristics of a cursor depend upon capabilities of the provider, the following advantages and disadvantages generally apply to the various types of cursors and locks.  
  
|Cursor or lock type|Advantages|Disadvantages|  
|-------------------------|----------------|-------------------|  
|**adOpenForwardOnly**|-   Low resource requirements|-   Cannot scroll backward<br />-   No data concurrency|  
|**adOpenStatic**|-   Scrollable|-   No data concurrency|  
|**adOpenKeyset**|-   Some data concurrency<br />-   Scrollable|-   Higher resource requirements<br />-   Not available in disconnected scenario|  
|**adOpenDynamic**|-   High data concurrency<br />-   Scrollable|-   Highest resource requirements<br />-   Not available in disconnected scenario|  
|**adLockReadOnly**|-   Low resource requirements<br />-   Highly scalable|-   Data not updatable through cursor|  
|**adLockBatchOptimistic**|-   Batch updates<br />-   Allows disconnected scenarios<br />-   Other users able to access data|-   Data can be changed by multiple users at once|  
|**adLockPessimistic**|-   Data cannot be changed by other users while locked|-   Prevents other users from accessing data while locked|  
|**adLockOptimistic**|-   Other users able to access data|-   Data can be changed by multiple users at once|
