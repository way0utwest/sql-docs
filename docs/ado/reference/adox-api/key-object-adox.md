---
title: "Key Object (ADOX) | Microsoft Docs"
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
  - "Key"
helpviewer_keywords: 
  - "Key object [ADOX]"
ms.assetid: 55f116fe-4d56-4892-bffe-0cdd6fc727c9
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Key Object (ADOX)
Represents a primary, foreign, or unique key field from a database table.  
  
## Remarks  
 The following code creates a new **Key**:  
  
```  
Dim obj As New Key  
```  
  
 With the properties and collections of a **Key** object, you can:  
  
-   Identify the key with the [Name](../../../ado/reference/adox-api/name-property-adox.md) property.  
  
-   Determine whether the key is primary, foreign, or unique with the [Type](../../../ado/reference/adox-api/type-property-key-adox.md) property.  
  
-   Access the database columns of the key with the [Columns](../../../ado/reference/adox-api/columns-collection-adox.md) collection.  
  
-   Specify the name of the related table with the [RelatedTable](../../../ado/reference/adox-api/relatedtable-property-adox.md) property.  
  
-   Determine the action performed on deletion or update of a primary key with the [DeleteRule](../../../ado/reference/adox-api/deleterule-property-adox.md) and [UpdateRule](../../../ado/reference/adox-api/updaterule-property-adox.md) properties.  
  
 This section contains the following topic.  
  
-   [Key Object Properties, Methods, and Events](../../../ado/reference/adox-api/key-object-properties-methods-and-events.md)  
  
## See Also  
 [Keys Append Method, Key Type, RelatedColumn, RelatedTable and UpdateRule Properties Example (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Columns Collection (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)   
 [Keys Collection (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)
