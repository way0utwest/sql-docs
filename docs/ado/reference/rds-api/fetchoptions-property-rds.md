---
title: "FetchOptions Property (RDS) | Microsoft Docs"
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
helpviewer_keywords: 
  - "FetchOptions property [ADO]"
ms.assetid: 7b2e254a-9354-4541-bc98-bb185276388f
caps.latest.revision: 15
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# FetchOptions Property (RDS)
Indicates the type of asynchronous fetching.  
  
> [!IMPORTANT]
>  Beginning with Windows 8 and Windows Server 2012, RDS server components are no longer included in the Windows operating system (see Windows 8 and [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) for more detail). RDS client components will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Applications that use RDS should migrate to [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## Setting and Return Values  
 Sets or returns one of the following values.  
  
|Constant|Description|  
|--------------|-----------------|  
|**adcFetchUpFront**|All the records of the [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) are fetched before control is returned to the application. The complete **Recordset** is fetched before the application is allowed to do anything with it.|  
|**adcFetchBackground**|Control can return to the application as soon as the first batch of records has been fetched. A subsequent read of the **Recordset** that attempts to access a record not fetched in the first batch will be delayed until the sought record is actually fetched, at which time control returns to the application.|  
|**adcFetchAsync**|Default. Control returns immediately to the application while records are fetched in the background. If the application attempts to read a record that hasn't yet been fetched, the record closest to the sought record will be read and control will return immediately, indicating that the current end of the **Recordset** has been reached. For example, a call to [MoveLast](../../../ado/reference/rds-api/movefirst-movelast-movenext-and-moveprevious-methods-rds.md) will move the current record position to the last record actually fetched, even though more records will continue to populate the **Recordset**.|  
  
> [!NOTE]
>  Each client-side executable file that uses these constants must provide declarations for them. You can cut and paste the constant declarations you want from the file Adcvbs.inc, located in the default installation folder for the RDS library.  
  
## Remarks  
 In a Web application, you will usually want to use **adcFetchAsync** (the default value), because it provides better performance. In a compiled client application, you will usually want to use **adcFetchBackground**.  
  
## Applies To  
 [DataControl Object (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## See Also  
 [ExecuteOptions and FetchOptions Properties Example (VBScript)](../../../ado/reference/rds-api/executeoptions-and-fetchoptions-properties-example-vbscript.md)   
 [Cancel Method (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)


