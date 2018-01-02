---
title: "sys.assemblies (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "system-catalog-views"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sys.assemblies"
  - "assemblies_TSQL"
  - "sys.assemblies_TSQL"
  - "assemblies"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.assemblies catalog view"
ms.assetid: e321753f-293f-42ab-b225-d118713df40b
caps.latest.revision: 29
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# sys.assemblies (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Returns a row for each assembly.  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Name of the assembly. Is unique within the database.|  
|**principal_id**|**int**|ID of the principal that owns this assembly.|  
|**assembly_id**|**int**|Assembly identification number. Is unique within a database.|  
|**clr_name**|**nvarchar(4000)**|Canonical string that encodes the simple name, version number, culture, public key, and architecture of the assembly. This value uniquely identifies the assembly on the common language runtime (CLR) side.|  
|**permission_set**|**tinyint**|Permission-set/security-level for assembly.<br /><br /> 1 = Safe Access<br /><br /> 2 = External Access<br /><br /> 3 = Unsafe Access|  
|**permission_set_desc**|**nvarchar(60)**|Description for permission-set/security-level for assembly.<br /><br /> SAFE_ACCESS<br /><br /> EXTERNAL_ACCESS<br /><br /> UNSAFE_ACCESS|  
|**is_visible**|**bit**|1 = Assembly is visible to register [!INCLUDE[tsql](../../includes/tsql-md.md)] entry points.<br /><br /> 0 = Assembly is intended only for managed callers. That is, the assembly provides internal implementation for other assemblies in the database.|  
|**create_date**|**datetime**|Date the assembly was created or registered.|  
|**modify_date**|**datetime**|Date the assembly was modified.|  
|**is_user_defined**|**bit**|Indicates the source of the assembly.<br /><br /> 0 = System-defined assemblies (such as Microsoft.SqlServer.Types for the **hierarchyid** data type)<br /><br /> 1 = User-defined assemblies|  
  
## Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] For more information, see [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## See Also  
 [CLR Assembly Catalog Views &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/clr-assembly-catalog-views-transact-sql.md)   
 [Catalog Views &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [ASSEMBLYPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/assemblyproperty-transact-sql.md)  
  
  
