---
title: "Migrating Triggers | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "in-memory-oltp"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine-imoltp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Migrating Triggers
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  This topic discusses DDL triggers and memory-optimized tables.  
  
 DML triggers are supported on memory-optimized tables, but only with the FOR | AFTER trigger event. For an example see [Implementing UPDATE with FROM or Subqueries](../../relational-databases/in-memory-oltp/implementing-update-with-from-or-subqueries.md). 
  
 LOGON triggers are triggers defined to fire on LOGON events. LOGON triggers do not affect memory-optimized tables.  
  
## DDL Triggers  
 DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.  
  
 You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it. You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.  
  
 You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.  
  
## See Also  
 [Migrating to In-Memory OLTP](../../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
