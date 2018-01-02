---
title: "Address Book Command Buttons | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "ado"
ms.technology:
  - "drivers"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "address book application scenario [ADO], command buttons"
  - "RDS scenarios [ADO], command buttons"
ms.assetid: 80676831-6488-4dad-a558-c47c52256a22
caps.latest.revision: 16
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Address Book Command Buttons
The Address Book application includes the following command buttons:  
  
-   A **Find** button to submit a query to the database.  
  
-   A **Clear** button to clear the text boxes before starting a new search.  
  
-   An **Update Profile** button to save changes to an employee record.  
  
-   A **Cancel Changes** button to discard changes.  
  
> [!IMPORTANT]
>  Beginning with Windows 8 and Windows Server 2012, RDS server components are no longer included in the Windows operating system (see Windows 8 and [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) for more detail). RDS client components will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Applications that use RDS should migrate to [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## Find Button  
 Clicking the **Find** button activates the VBScript Find_OnClick Sub procedure, which builds and sends the SQL query. Clicking this button populates the data grid.  
  
## Building the SQL Query  
 The first part of the Find_OnClick Sub procedure builds the SQL query, one phrase at a time, by appending text strings to a global SQL SELECT statement. It begins by setting the variable `myQuery` to a SQL SELECT statement that requests all rows of data from the data source table. Next, the Sub procedure scans each of the four input boxes on the page.  
  
 Because the program uses the word `like` in building the SQL statements, the queries are substring searches rather than exact matches.  
  
 For example, if the **Last Name** box contained the entry "Berge" and the **Title** box contained the entry "Program Manager", the SQL statement (value of `myQuery`) would read:  
  
```  
Select FirstName, LastName, Title, Email, Building, Room, Phone from Employee where lastname like 'Berge%' and title like 'Program Manager%'  
```  
  
 If the query was successful, all persons with a last name containing the text "Berge" (such as Berge and Berger) and with a title containing the words "Program Manager" (for example, Program Manager, Advanced Technologies) are displayed in the HTML data grid.  
  
## Preparing and Sending the Query  
 The last part of the Find_OnClick Sub procedure consists of two statements. The first statement assigns the [SQL](../../../ado/reference/rds-api/sql-property.md) property of the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object equal to the dynamically built SQL query. The second statement causes the **RDS.DataControl** object (`DC1`) to query the database, and then display the new results of the query in the grid.  
  
```  
Sub Find_OnClick  
   '...  
   DC1.SQL = myQuery  
   DC1.Refresh  
End Sub  
```  
  
## Update Profile Button  
 Clicking the **Update Profile** button activates the VBScript Update_OnClick Sub procedure, which executes the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object's (`DC1`) [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md) and [Refresh](../../../ado/reference/rds-api/refresh-method-rds.md) methods.  
  
```  
Sub Update_OnClick  
   DC1.SubmitChanges  
   DC1.Refresh  
End Sub  
```  
  
 When `DC1.SubmitChanges` executes, the Remote Data Service packages all the update information and sends it to the server via HTTP. The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned. `DC1.Refresh` isn't necessary after **SubmitChanges** with Remote Data Service, but it ensures fresh data.  
  
## Cancel Changes Button  
 Clicking **Cancel Changes** activates the VBScript Cancel_OnClick Sub procedure, which executes the [RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) object's (`DC1)` [CancelUpdate](../../../ado/reference/rds-api/cancelupdate-method-rds.md) method.  
  
```  
Sub Cancel_OnClick  
   DC1.CancelUpdate  
End Sub  
```  
  
 When `DC1.CancelUpdate` executes, it discards any edits that a user has made to an employee record on the data grid since the last query or update. It restores the original values.  
  
## See Also  
 [Address Book Navigation Buttons](../../../ado/guide/remote-data-service/address-book-navigation-buttons.md)   
 [DataControl Object (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)


