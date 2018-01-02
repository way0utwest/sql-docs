---
title: "Add a Root Node to JSON Output with the ROOT Option (SQL Server) | Microsoft Docs"
ms.custom: ""
ms.date: "06/02/2016"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine, sql-database"
ms.service: ""
ms.component: "json"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "dbe-json"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ROOT (FOR JSON)"
ms.assetid: b9afa74a-f59f-483e-a178-42be2e9882c9
caps.latest.revision: 16
author: "douglaslMS"
ms.author: "douglasl"
manager: "craigg"
ms.workload: "Inactive"
---
# Add a Root Node to JSON Output with the ROOT Option (SQL Server)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  To add a single, top-level element to the JSON output of the **FOR JSON** clause, specify the **ROOT** option.  
  
 If you don't specify the **ROOT** option, the JSON output doesn't include a root element.  
  
## Examples  
 The following table shows the output of the **FOR JSON** clause with and without the **ROOT** option.  
  
 The examples in the following table assume that the optional *RootName* argument is empty. If you provide a name for the root element, this value replaces the value **root** in the examples.  
  
 Without the **ROOT** option  
  
```json  
{  
   <<json properties>>  
}  
```  
  
```json  
[  
   <<json array elements>>  
]  
```  
  
 With the **ROOT** option  
  
```json  
{   
  "root": {  
   <<json properties>>  
 }  
}  
```  
  
```json  
{   
  "root": [  
   << json array elements >>  
  ]  
}  
```  
  
 Here's another example of a **FOR JSON** clause with the **ROOT** option. This example specifies a value for the optional *RootName* argument.  
  
 **Query**  
  
```sql  
SELECT TOP 5   
       BusinessEntityID As Id,  
       FirstName, LastName,  
       Title As 'Info.Title',  
       MiddleName As 'Info.MiddleName'  
   FROM Person.Person  
   FOR JSON PATH, ROOT('info')
```  
  
 **Result**  
  
```json  
{
	"info": [{
		"Id": 1,
		"FirstName": "Ken",
		"LastName": "Sánchez",
		"Info": {
			"MiddleName": "J"
		}
	}, {
		"Id": 2,
		"FirstName": "Terri",
		"LastName": "Duffy",
		"Info": {
			"MiddleName": "Lee"
		}
	}, {
		"Id": 3,
		"FirstName": "Roberto",
		"LastName": "Tamburello"
	}, {
		"Id": 4,
		"FirstName": "Rob",
		"LastName": "Walters"
	}, {
		"Id": 5,
		"FirstName": "Gail",
		"LastName": "Erickson",
		"Info": {
			"Title": "Ms.",
			"MiddleName": "A"
		}
	}]
}
```  
  
 **Result (without root)**  
  
```json  
[{
	"Id": 1,
	"FirstName": "Ken",
	"LastName": "Sánchez",
	"Info": {
		"MiddleName": "J"
	}
}, {
	"Id": 2,
	"FirstName": "Terri",
	"LastName": "Duffy",
	"Info": {
		"MiddleName": "Lee"
	}
}, {
	"Id": 3,
	"FirstName": "Roberto",
	"LastName": "Tamburello"
}, {
	"Id": 4,
	"FirstName": "Rob",
	"LastName": "Walters"
}, {
	"Id": 5,
	"FirstName": "Gail",
	"LastName": "Erickson",
	"Info": {
		"Title": "Ms.",
		"MiddleName": "A"
	}
}]
```  

## Learn more about the built-in JSON support in SQL Server  
For lots of specific solutions, use cases, and recommendations, see the [blog posts about the built-in JSON support](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) in SQL Server and in Azure SQL Database by Microsoft Program Manager Jovan Popovic.
 
## See Also  
 [FOR Clause &#40;Transact-SQL&#41;](../../t-sql/queries/select-for-clause-transact-sql.md)  
  
  
