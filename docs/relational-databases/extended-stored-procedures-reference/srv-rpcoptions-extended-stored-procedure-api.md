---
title: "srv_rpcoptions (Extended Stored Procedure API) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
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
  - "srv_rpcoptions"
apilocation: 
  - "opends60.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "srv_rpcoptions"
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
caps.latest.revision: 30
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# srv_rpcoptions (Extended Stored Procedure API)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Use CLR integration instead.  
  
 Returns run-time options for the current remote stored procedure.  
  
## Syntax  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
```  
  
## Arguments  
 *srvproc*  
 Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure). The structure contains information the the Extended Stored Procedure API library uses to manage communication and data between the application and the client.  
  
## Returns  
 A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure. If there is not a current remote stored procedure, 0 is returned and a message is generated.  
  
## Remarks  
 The following table describes each run-time flag.  
  
|Run-time flag|Description|  
|--------------------|-----------------|  
|SRV_NOMETADATA|The client has requested results without metadata information. This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. An Extended Stored Procedure API application cannot omit metadata information.|  
|SRV_RECOMPILE|The client has requested to recompile the remote stored procedure before executing it. This flag may not apply to an Extended Stored Procedure API application.|  
  
> [!IMPORTANT]  
>  You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server. For information about security review and testing, see this [Microsoft Web site](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
