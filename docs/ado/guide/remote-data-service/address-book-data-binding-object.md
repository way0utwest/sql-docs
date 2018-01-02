---
title: "Address Book Data-Binding Object | Microsoft Docs"
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
  - "RDS scenarios [ADO], data-binding object"
  - "address book application scenario [ADO], data-binding object"
ms.assetid: 080c1925-d453-4b89-92ac-c93591490518
caps.latest.revision: 14
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Address Book Data-Binding Object
The Address Book application uses the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object to bind data from the SQL Server database to a visual object (in this case, a DHTML table) in the application's client HTML page. The event-driven VBScript program logic uses the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) to:  
  
> [!IMPORTANT]
>  Beginning with Windows 8 and Windows Server 2012, RDS server components are no longer included in the Windows operating system (see Windows 8 and [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) for more detail). RDS client components will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Applications that use RDS should migrate to [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
-   Query the database, send updates to the database, and refresh the data grid.  
  
-   Allow users to move to the first, next, previous, or last record in the data grid.  
  
 The following code defines the **RDS.DataControl** component:  
  
```  
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33"  
   ID=DC1 Width=1 Height=1>  
   <PARAM NAME="SERVER" VALUE="http://<%=Request.ServerVariables("SERVER_NAME")%>">  
   <PARAM NAME="CONNECT" VALUE="Provider=sqloledb;  
Initial Catalog=AddrBookDb;Integrated Security=SSPI;">  
</OBJECT>  
```  
  
 The OBJECT tag defines the **RDS.DataControl** component in the program. The tag includes two types of parameters:  
  
-   Those associated with the generic OBJECT tag.  
  
-   Those specific to the **RDS.DataControl** object.  
  
## Generic OBJECT Tag Parameters  
 The following table describes the parameters associated with the OBJECT tag.  
  
|Parameter|Description|  
|---------------|-----------------|  
|***CLASSID***|A unique, 128-bit number that identifies the type of embedded object to the system. This identifier is maintained in the local computer's system registry. (For the class IDs of the **RDS.DataControl** object, see [RDS.DataControl Object](../../../ado/reference/rds-api/datacontrol-object-rds.md).)|  
|***ID***|Defines a document-wide identifier for the embedded object that is used to identify it in code.|  
  
## RDS.DataControl Tag Parameters  
 The following table describes the parameters specific to the **RDS.DataControl** object. (For a complete list of the **RDS.DataControl** object parameters, and when to implement them, see [RDS.DataControl object](../../../ado/reference/rds-api/datacontrol-object-rds.md).)  
  
|Parameter|Description|  
|---------------|-----------------|  
|[SERVER](../../../ado/reference/rds-api/server-property-rds.md)|If you are using HTTP, the value is the name of the server computer preceded by `http://`.|  
|[CONNECT](../../../ado/reference/rds-api/connect-property-rds.md)|Provides the necessary connection information for the **RDS.DataControl** to connect to SQL Server.|  
|[SQL](../../../ado/reference/rds-api/sql-property.md)|Sets or returns the query string used to retrieve the [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).|  
  
## See Also  
 [Address Book Command Buttons](../../../ado/guide/remote-data-service/address-book-command-buttons.md)


