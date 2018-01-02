---
title: "Microsoft Data Shaping Service for OLE DB (ADO Service Provider) | Microsoft Docs"
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
  - "providers [ADO], data shaping service for OLE DB"
  - "data shaping service for OLE DB [ADO]"
ms.assetid: 523009ce-e01b-4e2d-a7df-816d7688aff0
caps.latest.revision: 17
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Microsoft Data Shaping Service for OLE DB Overview
> [!IMPORTANT]
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Instead, applications should use XML.

 The Microsoft Data Shaping Service for OLE DB service provider supports the construction of hierarchical (shaped) [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) objects from a data provider.

## Provider Keyword
 To invoke the Data Shaping Service for OLE DB, specify the following keyword and value in the connection string.

```
"Provider=MSDataShape"
```

## Dynamic Properties
 When this service provider is invoked, the following dynamic properties are added to the [Properties](../../../ado/reference/ado-api/properties-collection-ado.md) collection of the[Connection](../../../ado/reference/ado-api/connection-object-ado.md) object.

|Dynamic Property Name|Description|
|---------------------------|-----------------|
|**Unique Reshape Names**|Indicates whether **Recordset** objects with duplicate values for their **Reshape Name** properties are allowed. If this dynamic property is **True** and a new **Recordset** is created with the same user-specified reshape name as an existing **Recordset**, then the new **Recordset** object's reshape name is modified to make it unique. If this property is **False** and a new **Recordset** is created with the same user-specified reshape name as the existing **Recordset**, both **Recordset** objects will have the same reshape name. Therefore, neither **Recordset** can be reshaped as long as both recordsets exist.<br /><br /> The default value of the property is **False**.|
|**Data Provider**|Indicates the name of the provider that will supply rows to be shaped. This value can be NONE if a provider will not be used to supply rows.|

 You can also set writable dynamic properties by specifying their names as keywords in the connection string. For example, in Microsoft Visual Basic, set the **Data Provider** dynamic property to "MSDASQL" by specifying:

```
Dim cn as New ADODB.Connection
cn.Open "Provider=MSDataShape;Data Provider=MSDASQL"
```

 You can also set or retrieve a dynamic property by specifying its name as the index to the [Properties](../../../ado/reference/ado-api/properties-collection-ado.md) property. For example, the following code example gets and prints the current value of the **Data Provider** dynamic property, then sets a new value if cn.DataProvider has been set to "MSDataShape" (either directly or indirectly through the connection string) and the connection has not been opened:

```
Debug.Print cn.Properties("Data Provider")
cn.Properties("Data Provider") = "MSDASQL"
```

> [!NOTE]
>  The dynamic property, **Data Provider**, can be set only on an unopened **Connection** object. Once the connection is opened, the **Data Provider** property becomes read-only.

 For more information about data shaping, see [Data Shaping](../../../ado/guide/data/data-shaping-overview.md).

## See Also
 [Appendix A: Providers](../../../ado/guide/appendixes/appendix-a-providers.md)
