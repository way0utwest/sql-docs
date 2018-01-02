---
title: "Restore a Database Protected by TDE in Parallel Data Warehouse"
author: "barbkess" 
ms.author: "barbkess"
manager: "jhubbard"	  
ms.prod: "analytics-platform-system"
ms.prod_service: "mpp-data-warehouse"
ms.service: ""
ms.component:
ms.suite: "sql"
ms.custom: ""
ms.technology: "mpp-data-warehouse"
description: "Use the following steps to restore a database that is encrypted by using transparent data encryption."
ms.date: "10/20/2016"
ms.topic: "article"
ms.assetid: ffb681ca-8598-4614-b06c-660376333fc3
caps.latest.revision: 4

---
# Restore a database protected by TDE
Use the following steps to restore a database that is encrypted by using transparent data encryption.  
  
The [Using Transparent Data Encryption](transparent-data-encryption.md#using-tde) example has code to enable TDE on the `AdventureWorksPDW2012` database. The following code continues that example, by creating a backup of the database on the original Analytics Platform System (APS) appliance, and then restoring the certificate and the database on a different appliance.  
  
The first step is to create a backup of the source database.  
  
```sql  
BACKUP DATABASE AdventureWorksPDW2012   
TO DISK = '\\SECURE_SERVER\Backups\AdventureWorksPDW2012';  
```  
  
Prepare the new SQL Server PDW for TDE by creating a master key, enabling encryption, and creating a network credential.  
  
```sql  
USE master;  
GO  
  
-- Create a database master key in the master database  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<UseStrongPasswordHere>';  
GO  
  
-- Enable encryption for PDW  
EXEC sp_pdw_database_encryption 1;  
GO  
  
EXEC sp_pdw_add_network_credentials 'SECURE_SERVER', '<domain>\<Windows_user>', '<password>';  
```  
  
The last two steps recreate the certificate by using the backups from the original SQL Server PDW. Use the password that you used when you created the backup of the certificate.  
  
```sql  
-- Create certificate in master  
CREATE CERTIFICATE MyServerCert  
    FROM FILE = '\\SECURE_SERVER\cert\MyServerCert.cer'   
    WITH PRIVATE KEY (FILE = '\\SECURE_SERVER\cert\MyServerCert.key',   
    DECRYPTION BY PASSWORD = '<password>');  
  
RESTORE DATABASE AdventureWorksPDW2012   
    FROM DISK = '\\SECURE_SERVER\Backups\AdventureWorksPDW2012';  
```  
  
## See Also  
[BACKUP DATABASE](../t-sql/statements/backup-database-parallel-data-warehouse.md)  
[CREATE MASTER KEY](../t-sql/statements/create-master-key-transact-sql.md) 
[sp_pdw_add_network_credentials](../relational-databases/system-stored-procedures/sp-pdw-add-network-credentials-sql-data-warehouse.md)  
[sp_pdw_database_encryption](../relational-databases/system-stored-procedures/sp-pdw-database-encryption-sql-data-warehouse.md)  
[CREATE CERTIFICATE](../t-sql/statements/create-certificate-transact-sql.md)  
[RESTORE DATABASE](../t-sql/statements/restore-database-parallel-data-warehouse.md)
  
