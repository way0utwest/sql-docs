---
title: "Implementing SQL_VARIANT in a Memory-Optimized Table | Microsoft Docs"
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
ms.assetid: f17f21df-959d-4e20-92f3-bd707d555a46
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Implementing SQL_VARIANT in a Memory-Optimized Table
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  Consider an example of a table with **SQL_VARIANT** column:  
  
```sql  
CREATE TABLE [dbo].[T1]([Key] [sql_variant] NOT NULL)  
```  
  
 Assume that the key column can only be either a **BIGINT** or **NVARCHAR(300)**. You can model this table as follows:  
  
```sql  
-- original disk-based table  
CREATE TABLE [dbo].[T1_disk]([Key] int not null primary key,  
       [Value] [sql_variant])  
go  
  
insert dbo.T1_disk values (1, 12345678)  
insert dbo.T1_disk values (2, N'my nvarchar')  
insert dbo.T1_disk values (3, NULL)  
go  
  
-- new memory-optimized table  
CREATE TABLE [dbo].[T1_inmem]([Key] INT NOT NULL PRIMARY KEY NONCLUSTERED,  
       [Value_bi] BIGINT,  
       [Value_nv] NVARCHAR(300),  
       [Value_enum] TINYINT NOT NULL) WITH (MEMORY_OPTIMIZED=ON)  
go  
  
-- copy data   
INSERT INTO dbo.T1_inmem  
  SELECT [Key],  
              CASE WHEN SQL_VARIANT_PROPERTY([Value], 'basetype') = 'bigint' THEN convert (bigint, [Value])  
              ELSE NULL END,  
              CASE WHEN SQL_VARIANT_PROPERTY([Value], 'basetype') != 'bigint' THEN convert (nvarchar(300), [Value])  
              ELSE NULL END,  
              CASE WHEN SQL_VARIANT_PROPERTY([Value], 'basetype') = 'bigint' THEN 1  
              ELSE 0 END  
  FROM dbo.T1_disk  
GO  
  
-- select data, converting back to sql_variant [will not work inside native proc]  
select [Key],   
       case [Value_enum] when 1 then convert(sql_variant, [Value_bi])   
    else convert(sql_variant, [Value_nv])   
    end  
from dbo.T1_inmem  
```  
  
 Now you can load data into [T1_HK] from T1 by opening a cursor on T1:  
  
```sql  
DECLARE T1_rows_cursor CURSOR FOR    
select *  
FROM dbo.T1  
  
OPEN T1_rows_cursor     
  
-- declare 1 variable each for column in HK table  
  
Declare  
@Key_biBIGINT = 0,  
@Key_nvnvarchar(300)= ' ',  
@Key_enumsmallint,  
@Keysql_variant  
  
FETCH NEXT FROM T1_rows_cursor INTO @key  
  
WHILE @@FETCH_STATUS = 0     
BEGIN     
  
-- setting the input parameters for inserting into the memory-optimized table  
-- convert SQL Variant types  
-- @key_enum =1 represents BIGINT  
if (SQL_VARIANT_PROPERTY(@Key, 'basetype') = 'bigint')  
begin  
set @key_bi = convert (bigint, @Key)  
set @key_enum = 1  
set @key_nv = 'invalid'  
end  
else  
begin  
set @Key_nv = convert (nvarchar (300), @Key)  
set @Key_enum = 0  
set @Key_bi = -1  
end  
  
-- inserting the row  
INSERT INTO T1_HK VALUES (@Key_bi, @Key_nv, @Key_enum)  
  
FETCH NEXT FROM T1_rows_cursor INTO @key  
END  
  
CLOSE T1_rows_cursor     
DEALLOCATE T1_rows_cursor  
```  
  
 You can convert data back to **SQL_VARIANT** as follows:  
  
```sql  
case [Key_enum] when 1 then convert(sql_variant, [Key_bi])   
                       else convert(sql_variant, [Key_nv])   
                       end  
```  
  
## See Also  
 [Migrating to In-Memory OLTP](../../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
