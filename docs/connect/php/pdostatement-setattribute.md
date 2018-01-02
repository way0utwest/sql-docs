---
title: "PDOStatement::setAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "07/13/2017"
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
ms.assetid: 329d9b5e-1c5d-40b0-9127-1051d0646fc7
caps.latest.revision: 20
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# PDOStatement::setAttribute
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Sets an attribute value, either a predefined PDO attribute or a custom driver attribute.  
  
## Syntax  
  
```  
  
bool PDOStatement::setAttribute ($attribute, $value );  
```  
  
#### Parameters  
$*attribute*: An integer, one of the PDO::ATTR_* or PDO::SQLSRV_ATTR_\* constants. See the Remarks section for the list of available attributes.  
  
$*value*: The (mixed) value to be set for the specified $*attribute*.  
  
## Return Value  
TRUE on success, FALSE otherwise.  
  
## Remarks  
The following table contains the list of available attributes:  
  
|Attribute|Values|Description|  
|-------------|----------|---------------|  
|PDO::SQLSRV_ATTR_CLIENT_BUFFER_MAX_KB_SIZE|1 to the PHP memory limit.|Configures the size of the buffer that holds the result set for a client-side cursor.<br /><br />The default is 10,240 KB (10 MB).<br /><br />For more information about client-side cursors, see [Cursor Types &#40;PDO_SQLSRV Driver&#41;](../../connect/php/cursor-types-pdo-sqlsrv-driver.md).|  
|PDO::SQLSRV_ATTR_ENCODING|Integer<br /><br />PDO::SQLSRV_ENCODING_UTF8 (Default)<br /><br />PDO::SQLSRV_ENCODING_SYSTEM<br /><br />PDO::SQLSRV_ENCODING_BINARY|Sets the character set encoding to be used by the driver to communicate with the server.|  
|PDO::SQLSRV_ATTR_FETCHES_NUMERIC_TYPE|true or false|Handles numeric fetches from columns with numeric SQL types (bit, integer, smallint, tinyint, float, or real).<br /><br />When connection option flag ATTR_STRINGIFY_FETCHES is on, the return value is a string even when SQLSRV_ATTR_FETCHES_NUMERIC_TYPE is on.<br /><br />When the returned PDO type in bind column is PDO_PARAM_INT, the return value from an integer column is an int even if SQLSRV_ATTR_FETCHES_NUMERIC_TYPE is off.|  
|PDO::SQLSRV_ATTR_QUERY_TIMEOUT|Integer|Sets the query timeout in seconds.<br /><br />By default, the driver will wait indefinitely for results. Negative numbers are not allowed.<br /><br />0 means no timeout.|  
  
## Example  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "", array('MultipleActiveResultSets'=>false )  );  
  
$stmt = $conn->prepare('SELECT * FROM Person.ContactType');  
  
echo $stmt->getAttribute( constant( "PDO::ATTR_CURSOR" ) );  
  
echo "\n";  
  
$stmt->setAttribute(PDO::SQLSRV_ATTR_QUERY_TIMEOUT, 2);  
echo $stmt->getAttribute( constant( "PDO::SQLSRV_ATTR_QUERY_TIMEOUT" ) );  
?>  
```  
  
## See Also  
[PDOStatement Class](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
