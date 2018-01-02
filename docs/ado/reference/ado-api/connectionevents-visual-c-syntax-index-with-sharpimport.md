---
title: "ConnectionEvents (Visual C++ Syntax Index with #import) | Microsoft Docs"
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
apitype: "COM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConnectionEvents collection [ADO], Visual C++ syntax index with #import"
ms.assetid: dd052d36-7730-4400-822b-0544fb1992b4
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ConnectionEvents (Visual C++ Syntax Index with #import)
## Events  
  
```  
HRESULT InfoMessage( struct Error * pError, enum  
    EventStatusEnum *     adStatus, struct _Connection * pConnection );  
  
HRESULT BeginTransComplete( long TransactionLevel,  
    struct Error * pError, enum EventStatusEnum * adStatus, struct  
    _Connection * pConnection );  
  
HRESULT CommitTransComplete( struct Error *  
    pError, enum EventStatusEnum     * adStatus, struct _Connection *  
    pConnection );  
  
HRESULT RollbackTransComplete( struct Error *  
    pError, enum     EventStatusEnum * adStatus, struct _Connection *  
    pConnection );  
  
HRESULT WillExecute( BSTR * Source, enum  
    CursorTypeEnum * CursorType,  
    enum LockTypeEnum * LockType, long * Options, enum EventStatusEnum *  
    adStatus, struct _Command * pCommand, struct _Recordset * pRecordset,  
    struct _Connection * pConnection );  
  
HRESULT ExecuteComplete( long RecordsAffected, struct  
    Error * pError,     enum EventStatusEnum * adStatus, struct _Command  
    * pCommand, struct     _Recordset * pRecordset, struct _Connection *  
    pConnection );  
  
HRESULT WillConnect( BSTR * ConnectionString, BSTR *  
    UserID, BSTR *     Password, long * Options, enum EventStatusEnum *  
    adStatus, struct     _Connection * pConnection );  
  
HRESULT ConnectComplete( struct Error *  
    pError, enum EventStatusEnum *     adStatus, struct _Connection *  
    pConnection );  
  
HRESULT Disconnect( enum EventStatusEnum *  
    adStatus, struct _Connection *     pConnection );  
```
