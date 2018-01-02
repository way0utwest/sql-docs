---
title: "Server Property (RDS) | Microsoft Docs"
ms.technology:
  - "drivers"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: 
ms.suite: sql
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.component: reference
ms.tgt_pltfrm: ""
ms.topic: "article"
apitype: "COM"
f1_keywords: 
  - "RDS::IBindMgr21::Server"
helpviewer_keywords: 
  - "Server property [RDS]"
ms.assetid: d2727ce7-da9f-4271-ae3c-9334ef477c14
caps.latest.revision: 18
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Server Property (RDS)
Indicates the Internet Information Services (IIS) name and communication protocol.  
  
 You can set the **Server** property at design time in the OBJECT tags of the[RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object, or at run time in scripting code.  
  
> [!IMPORTANT]
>  Beginning with Windows 8 and Windows Server 2012, RDS server components are no longer included in the Windows operating system (see Windows 8 and [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) for more detail). RDS client components will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Applications that use RDS should migrate to [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## Syntax  
 **HTTP**  
  
 Design-time syntax  
  
```  
  
<PARAM NAME="Server" VALUE="http:  
//awebsrvr:port  
">  
  
```  
  
 Run-time syntax  
  
```  
  
DataControl  
.Server="http://  
awebsrvr:port  
"  
  
```  
  
 **HTTPS**  
  
 Design-time syntax  
  
```  
  
<PARAM NAME="Server" VALUE="https://awebsrvr:port">  
```  
  
 Run-time syntax  
  
```  
  
DataControl.Server="https://awebsrvr:port"  
```  
  
 **DCOM**  
  
 Design-time syntax  
  
```  
  
<PARAM NAME="Server" VALUE="  
computername  
">  
  
```  
  
 Run-time syntax  
  
```  
  
DataControl.Server="computername"  
```  
  
 **In-process**  
  
 Design-time syntax  
  
```  
  
<PARAM NAME="Server" VALUE="">  
  
```  
  
 Run-time syntax  
  
```  
  
DataControl.Server=""  
```  
  
## Parameters  
 *awebsrvr*or *computername*  
 A **String** value that contains an Internet or intranet path, or computer name, if the server is on a remote computer; or, an empty string if the server is on the local computer.  
  
 *port*  
 Optional. A port that is used to connect to a server running IIS. The port number is set in Internet Explorer (on the **View** menu, click **Options**, and then select the **Connection** tab) or in IIS.  
  
 *DataControl*  
 An object variable that represents an **RDS.DataControl** object.  
  
## Remarks  
 The server is the location where the **RDS.DataControl** request (that is, a query or update) is processed. By default, all requests are processed by the [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) object, [MSDFMAP.Handler](../../../ado/guide/remote-data-service/datafactory-customization.md) component, and [MSDFMAP.INI](../../../ado/guide/remote-data-service/understanding-the-customization-file.md) file on the specified server. Remember that when changing servers to reconcile settings in the old and new **MSDFMAP.INI** files. Incompatibilities may cause requests that succeed on one server to fail on another. If the Server property is set to the empty string "", these objects will be used on the local computer.  
  
## Applies To  
 [DataControl Object (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## See Also  
 [Server Property Example (VBScript)](../../../ado/reference/rds-api/server-property-example-vbscript.md)   
 [Connect Property (RDS)](../../../ado/reference/rds-api/connect-property-rds.md)   
 [SQL Property](../../../ado/reference/rds-api/sql-property.md)   
 [SubmitChanges Method (RDS)](../../../ado/reference/rds-api/submitchanges-method-rds.md)


