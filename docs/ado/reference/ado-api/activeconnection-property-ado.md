---
title: "ActiveConnection Property (ADO) | Microsoft Docs"
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
f1_keywords: 
  - "Command15::ActiveConnection"
  - "Recordset15::get_ActiveConnection"
  - "_Record::ActiveConnection"
helpviewer_keywords: 
  - "ActiveConnection property [ADO]"
ms.assetid: 52d0a96c-14fb-4ad9-b004-4d821bc0a6db
caps.latest.revision: 12
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ActiveConnection Property (ADO)
Indicates to which [Connection](../../../ado/reference/ado-api/connection-object-ado.md) object the specified [Command](../../../ado/reference/ado-api/command-object-ado.md), [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md), or [Record](../../../ado/reference/ado-api/record-object-ado.md) object currently belongs.  
  
## Settings and Return Values  
 Sets or returns a **String** value that contains a definition for a connection if the connection is closed, or a **Variant** containing the current **Connection** object if the connection is open. Default is a null object reference. See the [ConnectionString](../../../ado/reference/ado-api/connectionstring-property-ado.md) property.  
  
## Remarks  
 Use the **ActiveConnection** property to determine the **Connection** object over which the specified **Command** object will execute or the specified **Recordset** will be opened.  
  
## Command  
 For **Command** objects, the **ActiveConnection** property is read/write.  
  
 If you attempt to call the [Execute](../../../ado/reference/ado-api/execute-method-ado-command.md) method on a **Command** object before setting this property to an open **Connection** object or valid connection string, an error occurs.  
  
 If a **Connection** object is assigned to the **ActiveConnection** property, the object must be opened. Assigning a closed Connection object causes an error.  
  
### Note  
 **Microsoft Visual Basic** Setting the **ActiveConnection** property to *Nothing* disassociates the **Command** object from the current **Connection** and causes the provider to release any associated resources on the data source. You can then associate the **Command** object with the same or another **Connection** object. Some providers allow you to change the property setting from one **Connection** to another, without having to first set the property to *Nothing*.  
  
 If the [Parameters](../../../ado/reference/ado-api/parameters-collection-ado.md) collection of the **Command** object contains parameters supplied by the provider, the collection is cleared if you set the **ActiveConnection** property to *Nothing* or to another **Connection** object. If you manually create [Parameter](../../../ado/reference/ado-api/parameter-object.md) objects and use them to fill the **Parameters** collection of the **Command** object, setting the **ActiveConnection** property to *Nothing* or to another **Connection** object leaves the **Parameters** collection intact.  
  
 Closing the **Connection** object with which a **Command** object is associated sets the **ActiveConnection** property to *Nothing*. Setting this property to a closed **Connection** object generates an error.  
  
## Recordset  
 For open **Recordset** objects or for **Recordset** objects whose [Source](../../../ado/reference/ado-api/source-property-ado-recordset.md) property is set to a valid **Command** object, the **ActiveConnection** property is read-only. Otherwise, it is read/write.  
  
 You can set this property to a valid **Connection** object or to a valid connection string. In this case, the provider creates a new **Connection** object using this definition and opens the connection. Additionally, the provider may set this property to the new **Connection** object to give you a way to access the **Connection** object for extended error information or to execute other commands.  
  
 If you use the *ActiveConnection* argument of the [Open](../../../ado/reference/ado-api/open-method-ado-recordset.md) method to open a **Recordset** object, the **ActiveConnection** property will inherit the value of the argument.  
  
 If you set the **Source** property of the **Recordset** object to a valid **Command** object variable, the **ActiveConnection** property of the **Recordset** inherits the setting of the **Command** object's **ActiveConnection** property.  
  
> [!NOTE]
>  **Remote Data Service Usage** When used on a client-side **Recordset** object, this property can be set only to a connection string or (in Microsoft Visual Basic or Visual Basic, Scripting Edition) to *Nothing*.  
  
## Record  
 This property is read/write when the **Record** object is closed, and may contain a connection string or reference to an open **Connection** object. This property is read-only when the **Record** object is open, and contains a reference to an open **Connection** object.  
  
 A **Connection** object is created implicitly when the **Record** object is opened from a URL. Open the **Record** with an existing, open **Connection** object by assigning the **Connection** object to this property, or using the **Connection** object as a parameter in the [Open](../../../ado/reference/ado-api/open-method-ado-record.md) method call. If the **Record** is opened from an existing **Record** or [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md), then it is automatically associated with that **Record** or **Recordset** object's **Connection** object.  
  
> [!NOTE]
>  URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md). For more information, see [Absolute and Relative URLs](../../../ado/guide/data/absolute-and-relative-urls.md).  
  
## Applies To  
  
||||  
|-|-|-|  
|[Command Object (ADO)](../../../ado/reference/ado-api/command-object-ado.md)|[Record Object (ADO)](../../../ado/reference/ado-api/record-object-ado.md)|[Recordset Object (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)|  
  
## See Also  
 [ActiveConnection, CommandText, CommandTimeout, CommandType, Size, and Direction Properties Example (VB)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vb.md)   
 [ActiveConnection, CommandText, CommandTimeout, CommandType, Size, and Direction Properties Example (VC++)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vc.md)   
 [ActiveConnection, CommandText, CommandTimeout, CommandType, Size, and Direction Properties Example (JScript)](../../../ado/reference/ado-api/activeconnection-commandtext-timeout-type-size-example-jscript.md)   
 [Connection Object (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)   
 [ConnectionString Property (ADO)](../../../ado/reference/ado-api/connectionstring-property-ado.md)
