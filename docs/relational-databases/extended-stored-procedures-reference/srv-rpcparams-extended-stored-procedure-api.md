---
title: "srv_rpcparams (Extended Stored Procedure API) | Microsoft Docs"
ms.custom: ""
ms.date: "03/04/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "extended-stored-procedures"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "srv_rpcparams"
apilocation: 
  - "opends60.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "srv_rpcparams"
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
caps.latest.revision: 30
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# srv_rpcparams (Extended Stored Procedure API)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Use CLR integration instead.  
  
 Returns the number of parameters for the current remote stored procedure.  
  
## Syntax  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
```  
  
## Arguments  
 *srvproc*  
 Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure). The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.  
  
## Returns  
 The number of parameters in the remote stored procedure. If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.  
  
## Remarks  
 This function returns the number of parameters in the current remote stored procedure. It is usually called from the remote stored procedure.  
  
 When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed). If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs. When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.  
  
> [!IMPORTANT]  
>  You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server. For information about security review and testing, see this [Microsoft Web site](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
