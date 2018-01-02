---
title: "Installing SSMA Components on SQL Server (DB2ToSQL) | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssma-db2"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "sql-ssma"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Azure SQL Database"
  - "SQL Server"
ms.assetid: cf2b724b-4ca7-470a-8dd7-fa95b1e060a4
caps.latest.revision: 6
author: "Shamikg"
ms.author: "Shamikg"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Installing SSMA Components on SQL Server (DB2ToSQL)
In this version of SSMA there is no need for a separate install on [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] of the SSMA extension pack, which supports data migration, and DB2 providers to enable server-to-server connectivity.  
  
## SSMA for DB2 Extension Pack  
The SSMA extension pack adds a schema the database in the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. The **sysdb** schema contains the tables and stored procedures that are required to migrate data, and the user-defined functions that emulate DB2 system functions.  
  
## See Also  
[Installing SSMA for DB2 Client &#40;DB2ToSQL&#41;](../../ssma/db2/installing-ssma-for-db2-client-db2tosql.md)  
[Migrating DB2 Databases to SQL Server &#40;DB2ToSQL&#41;](../../ssma/db2/migrating-db2-databases-to-sql-server-db2tosql.md)  
  
