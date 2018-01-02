---
title: "Using an SQL Statement to Modify Data | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "jdbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4704199b-c0ae-4c77-8a2e-6963715b4ffb
caps.latest.revision: 17
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Using an SQL Statement to Modify Data
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  To modify the data that is contained in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] database by using an SQL statement, you can use the [executeUpdate](../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md) method of the [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md) class. The executeUpdate method will pass the SQL statement to the database for processing, and then return a value that indicates the number of rows that were affected.  
  
 To do this, you must first create a SQLServerStatement object by using the [createStatement](../../connect/jdbc/reference/createstatement-method-sqlserverconnection.md) method of the [SQLServerConnection](../../connect/jdbc/reference/sqlserverconnection-class.md) class.  
  
 In the following example, an open connection to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] sample database is passed in to the function, an SQL statement is constructed that adds new data to the table, and then the statement is run and the return value is displayed.  
  
 [!code[JDBC#UsingSQLToModifyData1](../../connect/jdbc/codesnippet/Java/using-an-sql-statement-t_1_1.java)]  
  
> [!NOTE]  
>  If you must use an SQL statement that contains parameters to modify the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] database, you should use the [executeUpdate](../../connect/jdbc/reference/executeupdate-method-sqlserverpreparedstatement.md) method of the [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) class.  
>   
>  If the column that you are trying to insert data into contains special characters such as spaces, you must provide the values to be inserted, even if they are default values. If you do not, the insert operation will fail.  
>   
>  If you want the JDBC driver to return all update counts, including update counts returned by any triggers that may have fired, set the lastUpdateCount connection string property to "false". For more information about the lastUpdateCount property, see [Setting the Connection Properties](../../connect/jdbc/setting-the-connection-properties.md).  
  
## See Also  
 [Using Statements with SQL](../../connect/jdbc/using-statements-with-sql.md)  
  
  
