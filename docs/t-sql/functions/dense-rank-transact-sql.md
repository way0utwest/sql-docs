---
title: "DENSE_RANK (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/16/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "t-sql|functions"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "DENSE_RANK_TSQL"
  - "DENSE_RANK"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "row ranking [SQL Server]"
  - "DENSE_RANK function"
  - "tied rows [SQL Server]"
  - "ranking rows"
ms.assetid: 03871fc6-9592-4016-b0b2-ff543f132b20
caps.latest.revision: 47
author: "edmacauley"
ms.author: "edmaca"
manager: "craigg"
ms.workload: "Active"
---
# DENSE_RANK (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Returns the rank of rows within the partition of a result set, without any gaps in the ranking. The rank of a row is one plus the number of distinct ranks that come before the row in question.  
  
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
DENSE_RANK ( ) OVER ( [ <partition_by_clause> ] < order_by_clause > )  
```  
  
## Arguments  
 \<partition_by_clause>  
 Divides the result set produced by the [FROM](../../t-sql/queries/from-transact-sql.md) clause into partitions to which the DENSE_RANK function is applied. For the PARTITION BY syntax, see [OVER Clause &#40;Transact-SQL&#41;](../../t-sql/queries/select-over-clause-transact-sql.md).  
  
 \<order_by_clause>  
 Determines the order in which the DENSE_RANK function is applied to the rows in a partition.  
  
## Return Types  
 **bigint**  
  
## Remarks  
 If two or more rows tie for a rank in the same partition, each tied rows receives the same rank. For example, if the two top salespeople have the same SalesYTD value, they are both ranked one. The salesperson with the next highest SalesYTD is ranked number two. This is one more than the number of distinct rows that come before this row. Therefore, the numbers returned by the DENSE_RANK function do not have gaps and always have consecutive ranks.  
  
 The sort order used for the whole query determines the order in which the rows appear in a result. This implies that a row ranked number one does not have to be the first row in the partition.  
  
 DENSE_RANK is nondeterministic. For more information, see [Deterministic and Nondeterministic Functions](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md).  
  
## Examples  
  
### A. Ranking rows within a partition  
 The following example ranks the products in inventory the specified inventory locations according to their quantities. The result set is partitioned by `LocationID` and logically ordered by `Quantity`. Notice that products 494 and 495 have the same quantity. Because they are tied, they are both ranked one.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT i.ProductID, p.Name, i.LocationID, i.Quantity  
    ,DENSE_RANK() OVER   
    (PARTITION BY i.LocationID ORDER BY i.Quantity DESC) AS Rank  
FROM Production.ProductInventory AS i   
INNER JOIN Production.Product AS p   
    ON i.ProductID = p.ProductID  
WHERE i.LocationID BETWEEN 3 AND 4  
ORDER BY i.LocationID;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
ProductID   Name                               LocationID Quantity Rank  
----------- ---------------------------------- ---------- -------- -----  
494         Paint - Silver                     3          49       1  
495         Paint - Blue                       3          49       1  
493         Paint - Red                        3          41       2  
496         Paint - Yellow                     3          30       3  
492         Paint - Black                      3          17       4  
495         Paint - Blue                       4          35       1  
496         Paint - Yellow                     4          25       2  
493         Paint - Red                        4          24       3  
492         Paint - Black                      4          14       4  
494         Paint - Silver                     4          12       5  
  
(10 row(s) affected)  
  
```  
  
### B. Ranking all rows in a result set  
 The following example returns the top ten employees ranked by their salary. Because a PARTITION BY clause was not specified, the DENSE_RANK function was applied to all rows in the result set.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT TOP(10) BusinessEntityID, Rate,   
       DENSE_RANK() OVER (ORDER BY Rate DESC) AS RankBySalary  
FROM HumanResources.EmployeePayHistory;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
BusinessEntityID Rate                  RankBySalary  
---------------- --------------------- --------------------  
1                125.50                1  
25               84.1346               2  
273              72.1154               3  
2                63.4615               4  
234              60.0962               5  
263              50.4808               6  
7                50.4808               6  
234              48.5577               7  
285              48.101                8  
274              48.101                8  
```  
  
## C. Four ranking functions used in the same query  
 The following shows the four ranking functions used in the same query. For function specific examples, see each ranking function.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT p.FirstName, p.LastName  
    ,ROW_NUMBER() OVER (ORDER BY a.PostalCode) AS "Row Number"  
    ,RANK() OVER (ORDER BY a.PostalCode) AS Rank  
    ,DENSE_RANK() OVER (ORDER BY a.PostalCode) AS "Dense Rank"  
    ,NTILE(4) OVER (ORDER BY a.PostalCode) AS Quartile  
    ,s.SalesYTD  
    ,a.PostalCode  
FROM Sales.SalesPerson AS s   
    INNER JOIN Person.Person AS p   
        ON s.BusinessEntityID = p.BusinessEntityID  
    INNER JOIN Person.Address AS a   
        ON a.AddressID = p.BusinessEntityID  
WHERE TerritoryID IS NOT NULL AND SalesYTD <> 0;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
|FirstName|LastName|Row Number|Rank|Dense Rank|Quartile|SalesYTD|PostalCode|  
|---------------|--------------|----------------|----------|----------------|--------------|--------------|----------------|  
|Michael|Blythe|1|1|1|1|4557045.0459|98027|  
|Linda|Mitchell|2|1|1|1|5200475.2313|98027|  
|Jillian|Carson|3|1|1|1|3857163.6332|98027|  
|Garrett|Vargas|4|1|1|1|1764938.9859|98027|  
|Tsvi|Reiter|5|1|1|2|2811012.7151|98027|  
|Shu|Ito|6|6|2|2|3018725.4858|98055|  
|José|Saraiva|7|6|2|2|3189356.2465|98055|  
|David|Campbell|8|6|2|3|3587378.4257|98055|  
|Tete|Mensa-Annan|9|6|2|3|1931620.1835|98055|  
|Lynn|Tsoflias|10|6|2|3|1758385.926|98055|  
|Rachel|Valdez|11|6|2|4|2241204.0424|98055|  
|Jae|Pak|12|6|2|4|5015682.3752|98055|  
|Ranjit|Varkey Chudukatil|13|6|2|4|3827950.238|98055| 


## Examples: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] and [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### D: Ranking rows within a partition  
 The following example ranks the sales representatives in each sales territory according to their total sales. The rowset is partitioned by `SalesTerritoryGroup` and sorted by `SalesAmountQuota`.  
  
```  
-- Uses AdventureWorks  
  
SELECT LastName, SUM(SalesAmountQuota) AS TotalSales, SalesTerritoryGroup,  
    DENSE_RANK() OVER (PARTITION BY SalesTerritoryGroup ORDER BY SUM(SalesAmountQuota) DESC ) AS RankResult  
FROM dbo.DimEmployee AS e  
INNER JOIN dbo.FactSalesQuota AS sq ON e.EmployeeKey = sq.EmployeeKey  
INNER JOIN dbo.DimSalesTerritory AS st ON e.SalesTerritoryKey = st.SalesTerritoryKey  
WHERE SalesPersonFlag = 1 AND SalesTerritoryGroup != N'NA'  
GROUP BY LastName,SalesTerritoryGroup;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```
 LastName          TotalSales     SalesTerritoryGroup  RankResult  
----------------  -------------  -------------------  --------  
Pak               10514000.0000  Europe               1  
Varkey Chudukatil  5557000.0000  Europe               2  
Valdez             2287000.0000  Europe               3  
Carson            12198000.0000  North America        1  
Mitchell          11786000.0000  North America        2  
Blythe            11162000.0000  North America        3  
Reiter             8541000.0000  North America        4  
Ito                7804000.0000  North America        5  
Saraiva            7098000.0000  North America        6  
Vargas             4365000.0000  North America        7  
Campbell           4025000.0000  North America        8  
Ansman-Wolfe       3551000.0000  North America        9  
Mensa-Annan        2753000.0000  North America        10  
Tsoflias           1687000.0000  Pacific              1 
```  

## See Also  
 [RANK &#40;Transact-SQL&#41;](../../t-sql/functions/rank-transact-sql.md)   
 [ROW_NUMBER &#40;Transact-SQL&#41;](../../t-sql/functions/row-number-transact-sql.md)   
 [NTILE &#40;Transact-SQL&#41;](../../t-sql/functions/ntile-transact-sql.md)   
 [Ranking Functions &#40;Transact-SQL&#41;](../../t-sql/functions/ranking-functions-transact-sql.md)   
 [Functions](../../t-sql/functions/functions.md)  
  
  

