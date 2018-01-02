---
title: "Collections (Visual C++ Syntax Index with #import) | Microsoft Docs"
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
  - "syntax indexes [ADO], ADO for Visual C++ syntax with #import"
  - "collections [ADO], ADO for Visual C++ syntax with #import"
  - "ADO for Visual C++ syntax with #import [ADO]"
  - "#import [ADO]"
ms.assetid: 36fbca8e-1884-44b5-806b-d15e30f42fe6
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Collections (Visual C++ Syntax Index with #import)
It is useful to know that collections inherit certain common methods and properties.  
  
 All collections inherit the **Count** property and **Refresh** method, and all collections add the **Item** property. The **Errors** collection adds the **Clear** method. The **Parameters** collection inherits the **Append** and **Delete** methods, while the **Fields** collection adds the **Append**, **Delete**, and **Update** methods.  
  
## Properties Collection  
  
### Methods  
  
```  
HRESULT Refresh( );  
```  
  
### Properties  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## Errors Collection  
  
### Methods  
  
```  
HRESULT Clear( );  
HRESULT Refresh( );  
```  
  
### Properties  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## Parameters Collection  
  
### Methods  
  
```  
HRESULT Append( IDispatch * Object );  
HRESULT Delete( const _variant_t & Index );  
HRESULT Refresh( );  
```  
  
### Properties  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## Fields Collection  
  
### Methods  
  
```  
HRESULT Append( _bstr_t Name, enum DataTypeEnum Type, long DefinedSize, enum FieldAttributeEnum Attrib, const _variant_t & FieldValue = vtMissing );  
HRESULT Delete( const _variant_t & Index );  
HRESULT Refresh( );  
HRESULT Update( );  
```  
  
### Properties  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## See Also  
 [Errors Collection (ADO)](../../../ado/reference/ado-api/errors-collection-ado.md)   
 [Fields Collection (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)   
 [Parameters Collection (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)   
 [Properties Collection (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
