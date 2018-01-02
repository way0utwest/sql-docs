---
title: "Breaking Changes to Database Engine Features in SQL Server 2017 | Microsoft Docs"
description: "Breaking changes to Database Engine Features in SQL Server 2017"
ms.date: "04/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "database-engine"
ms.reviewer: ""
ms.suite: "sql"
ms.custom: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "breaking changes 2017 [SQL Server]"
ms.assetid: 
caps.latest.revision: 1
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Breaking Changes to Database Engine Features in [!INCLUDE[sssqlv14-md](../includes/sssqlv14-md.md)]
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]


  This topic describes breaking changes in the [!INCLUDE[sssqlv14-md](../includes/sssqlv14-md.md)][!INCLUDE[ssDE](../includes/ssde-md.md)]. These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. You might encounter these issues when you upgrade.  
  
## Breaking Changes in [!INCLUDE[sssqlv14-md](../includes/sssqlv14-md.md)][!INCLUDE[ssDE](../includes/ssde-md.md)]  
  
-  CLR uses Code Access Security (CAS) in the .NET Framework, which is no longer supported as a security boundary. Beginning with [!INCLUDE[sssqlv14-md](../includes/sssqlv14-md.md)][!INCLUDE[ssDE](../includes/ssde-md.md)], an `sp_configure` option called `clr strict security` is introduced to enhance the security of CLR assemblies. clr strict security is enabled by default, and treats `SAFE` and `EXTERNAL_ACCESS` CLR assemblies as if they were marked `UNSAFE`. The `clr strict security` option can be disabled for backward compatibility, but this is not recommended. When `clr strict security` is disabled, a CLR assembly created with `PERMISSION_SET = SAFE` may be able to access external system resources, call unmanaged code, and acquire **sysadmin** privileges. After enabling strict security, any assemblies that are not signed will fail to load. Also, if a database has `SAFE` or `EXTERNAL_ACCESS` assemblies, `RESTORE` or `ATTACH DATABASE` statements can complete, but the assemblies may fail to load.   
  To load the assemblies, you must either alter or drop and recreate each assembly so that it is signed with a certificate or asymmetric key that has a corresponding login with the `UNSAFE ASSEMBLY` permission on the server. For more information, see [CLR strict security](../database-engine/configure-windows/clr-strict-security.md). 


  
## Previous Versions  

-   [Breaking Changes to Database Engine Features in SQL Server 2016](../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md)  
  
-   [Breaking Changes to Database Engine Features in SQL Server 2014](https://msdn.microsoft.com/library/ms143179\(v=sql.120\))  
  
-   [Breaking Changes to Database Engine Features in SQL Server 2012](https://msdn.microsoft.com/library/ms143179\(v=sql.110\))  
  
-   [Breaking Changes to Database Engine Features in SQL Server 2008](https://msdn.microsoft.com/library/ms143179\(v=sql.100\))  
  
## See Also  
 [Deprecated Database Engine Features in SQL Server 2016](../database-engine/deprecated-database-engine-features-in-sql-server-2016.md)   
 [Discontinued Database Engine Functionality in SQL Server 2016](../database-engine/discontinued-database-engine-functionality-in-sql-server-2016.md)   
 [SQL Server Database Engine Backward Compatibility](../database-engine/sql-server-database-engine-backward-compatibility.md)   
 [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](../t-sql/statements/alter-database-transact-sql-compatibility-level.md)  
  
  
