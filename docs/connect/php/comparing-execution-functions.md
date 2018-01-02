---
title: "Comparing Execution Functions | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "php"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "executing queries"
ms.assetid: 130fc0fd-87dd-46b2-918f-de9dc572c769
caps.latest.revision: 18
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Comparing Execution Functions
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

The [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] provides several options for executing functions.  
  
If you are using the SQLSRV driver, use [sqlsrv_query](../../connect/php/sqlsrv-query.md) to execute a single query and [sqlsrv_prepare](../../connect/php/sqlsrv-prepare.md) with [sqlsrv_execute](../../connect/php/sqlsrv-execute.md) to execute a prepared statement multiple times with different parameter values for each execution.  
  
If you are using the PDO_SQLSRV driver, you can execute a query with one of the following:  
  
-   [PDO::exec](../../connect/php/pdo-exec.md)  
  
-   [PDO::query](../../connect/php/pdo-query.md)  
  
-   [PDO::prepare](../../connect/php/pdo-prepare.md) and [PDOStatement::execute](../../connect/php/pdostatement-execute.md).  
  
## See Also  
[SQLSRV Driver API Reference](../../connect/php/sqlsrv-driver-api-reference.md)  
[PDO_SQLSRV Driver Reference](../../connect/php/pdo-sqlsrv-driver-reference.md)  
[Programming Guide for PHP SQL Driver](../../connect/php/programming-guide-for-php-sql-driver.md)
  
