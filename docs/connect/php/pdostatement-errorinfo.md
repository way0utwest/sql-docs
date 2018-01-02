---
title: "PDOStatement::errorInfo | Microsoft Docs"
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
ms.assetid: e45bebe8-ea4c-49b6-93db-cf1ae65f530c
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# PDOStatement::errorInfo
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Retrieves extended error information of the most recent operation on the statement handle.  
  
## Syntax  
  
```  
  
array PDOStatement::errorInfo();  
```  
  
## Return Value  
An array of error information about the most recent operation on the statement handle. The array consists of the following fields:  
  
-   The SQLSTATE error code  
  
-   The driver-specific error code  
  
-   The driver-specific error message  
  
If there is no error, or if the SQLSTATE is not set, the driver-specific fields will be NULL.  
  
## Remarks  
Support for PDO was added in version 2.0 of the [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## Example  
In this example, the SQL statement has an error, which is then reported.  
  
```  
<?php  
$conn = new PDO( "sqlsrv:server=(local) ; Database = AdventureWorks", "", "");  
$stmt = $conn->prepare('SELECT * FROM Person.Addressx');  
  
$stmt->execute();  
print_r ($stmt->errorInfo());  
?>  
```  
  
## See Also  
[PDOStatement Class](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
