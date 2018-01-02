---
title: "ExecuteOptions Property (RDS) | Microsoft Docs"
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
  - "ExecuteOptions property [ADO], VBScript example"
ms.assetid: 62a4fd88-afc3-4f1f-b978-40710a30c4e9
caps.latest.revision: 15
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ExecuteOptions Property (RDS)
Indicates whether asynchronous execution is enabled.  
  
> [!IMPORTANT]
>  Beginning with Windows 8 and Windows Server 2012, RDS server components are no longer included in the Windows operating system (see Windows 8 and [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) for more detail). RDS client components will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Applications that use RDS should migrate to [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## Settings and Return Values  
 Sets or returns one of the following values.  
  
|Constant|Description|  
|--------------|-----------------|  
|**adcExecSync**|Executes the next refresh of the [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) synchronously.|  
|**adcExecAsync**|Default. Executes the next refresh of the **Recordset** asynchronously.|  
  
> [!NOTE]
>  Each executable file that uses these constants must provide declarations for them. You can cut and paste the constant declarations that you want from the file Adcvbs.inc, located in the default installation folder for the RDS library.  
  
## Remarks  
 If **ExecuteOptions** is set to **adcExecAsync**, then this asynchronously executes the next **Refresh** call on the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object's **Recordset**.  
  
 If you try to call [Reset](../../../ado/reference/rds-api/reset-method-rds.md), [Refresh](../../../ado/reference/rds-api/refresh-method-rds.md), [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md), [CancelUpdate](../../../ado/reference/ado-api/cancelupdate-method-ado.md), or [Recordset](../../../ado/reference/rds-api/recordset-sourcerecordset-properties-rds.md) while another asynchronous operation that might change the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object's **Recordset** is executing, an error occurs.  
  
 If an error occurs during an asynchronous operation, the **RDS.DataControl** object's [ReadyState](../../../ado/reference/rds-api/readystate-property-rds.md) value changes from **adcReadyStateLoaded** to **adcReadyStateComplete**, and the **Recordset** property value remains *Nothing*.  
  
## Applies To  
 [DataControl Object (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## See Also  
 [ExecuteOptions and FetchOptions Properties Example (VBScript)](../../../ado/reference/rds-api/executeoptions-and-fetchoptions-properties-example-vbscript.md)   
 [Cancel Method (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)


