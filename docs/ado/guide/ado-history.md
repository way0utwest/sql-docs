---
title: "ADO History | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.tgt_pltfrm: ""
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "ado"
ms.technology: “drivers”
ms.topic: "article"
helpviewer_keywords:
  - "ADO, what's new"
ms.assetid: 667673f2-3151-432b-894a-3fc60b704ea4
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ADO Features for each Release
This topic lists the new features introduced by each release of ADO, ADO MD, and ADOX.

## ADO 6.0
 ADO 6.0 is included in Windows Vista, as a part of the Windows Data Access Components (Windows DAC) 6.0. ADO 6.0 is functionally equivalent to ADO 2.8.

## ADO 2.8
 ADO 2.8 was included in Windows XP and Windows Server 2003, as part of the Microsoft Data Access Components (MDAC) 2.8. A redistributable version of MDAC 2.8 is also available; note that this redistributable version should only be installed on Windows 2000. ADO 2.8 addresses several security-related concerns:

 *Hard drive access is not allowed outside a trusted zone.*
 In cross-domain scripting involving nontrusted sites, the following operations are disabled: **Stream.SaveToFile**, **Stream.LoadFromFile**, **Recordset.Save**, and **Recordset.Open**, used in conjunction with the **adCmdFile** flag or with the Microsoft OLE DB Persistence Provider (MSPersist).

 **Recordset.Open** *,*  **Recordset.Save** *,*  **Stream.SaveToFile** *, and*  **Stream.LoadFromFile**  *operate on physical files only.*
 These methods now verify that file handles point to physical files only.

 **Recordset.ActiveCommand**  *returns an error when invoked from an HTML/ASP page.*
 This prevents the **Command** object from being misused.

 *The number of*  **Recordsets**  *returned by a nested*  **Shape**  *command has an upper bound.*
 A nested shape command now returns a maximum of 512 **Recordsets**. This means that a **Shape** command can no longer be nested at any depth. Instead, the maximum level depth is 512, if each command results in a single (child) **Recordset**. If, at any level, a **Shape** command returns multiple **Recordsets**, the maximum level of depth will be less than 512.

## ADO 2.7
 *64-bit platform support*
 ADO 2.7 introduces support for 64-bit processors.

## ADO 2.6
 **CubDef.GetSchemaObject**  *Method*
 Starting with ADO 2.6, ADO MD objects can be retrieved using unique names, as specified by the [UniqueName property (ADO MD)](../../ado/reference/ado-md-api/uniquename-property-ado-md.md). The names of parent objects do not need to be known, and parent collections do not need to be populated to retrieve a schema object. See [GetSchemaObject method (ADO MD)](../../ado/reference/ado-md-api/getschemaobject-method-ado-md.md).

 *Command streams*
 The **Command** object supports commands in stream format as an alternative to using the **CommandText** property. The [CommandStream property (ADO)](../../ado/reference/ado-api/commandstream-property-ado.md) can be used to specify XML Templates or updategrams as the **Command** input with the Microsoft OLE DB Provider for SQL Server.

 **Dialect**  *property*
 [Dialect](../../ado/reference/ado-api/dialect-property.md) is a new property that defines the syntax and general rules that the provider uses to parse the string or stream.

 **Command.Execute**  *method*
 The [Execute method](../../ado/reference/ado-api/execute-method-ado-command.md) of the ADO **Command** object has been enhanced to use streams for input and output.

 *Field statusvalues*
 If the user encounters a DB_E_ERRORSOCCURRED error when modifying a **Field** of a **Recordset**, ADO will now fill the **Field.Status** property with the appropriate status information so that the user will have more information about what went wrong. See [Status Property (ADO Field)](../../ado/reference/ado-api/status-property-ado-field.md).

 **NamedParameters**  *property*
 [NamedParameters](../../ado/reference/ado-api/namedparameters-property-ado.md) is a new property of the **Command** object that indicates that the provider should use named parameters.

 *Resultsets in streams*
 ADO can return resultsets from a data source in a **Stream**, rather than a **Recordset** object. Using the latest version of the Microsoft OLE DB Provider for SQL Server, you can get XML results from the provider by executing a "For XML" query. A **Stream** that receives the resultset can be opened with a "For XML" command as the source. See [Retrieving Resultsets into Streams](../../ado/guide/data/retrieving-resultsets-into-streams.md).

 *Single row resultset*
 The ADO **Record** object can now be opened on a command string or **Command** object that returns one row of data from the provider. This results in improved performance with MDAC 2.6 providers. See [Open Method (ADO Record)](../../ado/reference/ado-api/open-method-ado-record.md).

## ADO 2.5
 **Record** *object*
 ADO 2.5 introduces the **Record** object to represent and manage a row from a **Recordset** or a data provider, or an object encapsulating a semi-structured data, such as a file or directory.

 **Stream** *object*
 ADO 2.5 also introduces the **Stream** object to represent a stream of binary or text data.

 *URL binding*
 ADO 2.5 introduces the use of a URL, as an alternative to a connection string and command text, to name data store objects. A URL can be used with the existing **Connection** and **Recordset** objects, as well as with the new **Record** and **Stream** objects.

 *Data providers supporting URL binding*
 ADO 2.5 supports OLE DB providers that recognize the URL schemes. This includes OLE DB Provider for Internet Publishing, which accesses the Windows 2000 file system and recognizes the existing HTTP scheme.
