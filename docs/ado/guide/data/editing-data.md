---
title: "Editing Data | Microsoft Docs"
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
  - "ADO, editing data"
  - "AdUseClient [ADO]"
  - "editing data [ADO]"
ms.assetid: ef514f85-c446-4f05-824e-c9313b2ffae1
caps.latest.revision: 16
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Editing Data
We have explained how use ADO to connect to a data source, execute a command, get the results in a **Recordset** object, and navigate within the **Recordset**. This section focuses on the next fundamental ADO operation: editing data.  
  
 This section continues to use the sample **Recordset** introduced in [Examining Data](../../../ado/guide/data/examining-data.md), with one important change. The following code is used to open the **Recordset**:  
  
```  
'BeginEditIntro  
    Dim strSQL As String  
    Dim objRs1 As ADODB.Recordset  
  
    strSQL = "SELECT * FROM Shippers"  
  
    Set objRs1 = New ADODB.Recordset  
  
    objRs1.Open strSQL, GetNewConnection, adOpenStatic, _  
                adLockBatchOptimistic, adCmdText  
  
    ' Disconnect the Recordset from the Connection object.  
    Set objRs1.ActiveConnection = Nothing  
'EndEditIntro  
```  
  
 The important change to the code involves setting the **CursorLocation** property of the **Connection** object equal to **adUseClient** in the *GetNewConnection* function (shown in the next example), which indicates the use of a client cursor. For more information about the differences between client-side and server-side cursors, see [Understanding Cursors and Locks](../../../ado/guide/data/understanding-cursors-and-locks.md).  
  
 The **CursorLocation** property's **adUseClient** setting moves the location of the cursor from the data source (the SQL Server, in this case) to the location of the client code (the desktop workstation). This setting forces ADO to invoke the Client Cursor Engine for OLE DB on the client in order to create and manage the cursor.  
  
 You might also have noticed that the **LockType** parameter of the **Open** method changed to **adLockBatchOptimistic**. This opens the cursor in batch mode. (The provider caches multiple changes and writes them to the underlying data source only when you call the **UpdateBatch** method.) Changes that were made to the **Recordset** will not be updated in the database until the **UpdateBatch** method is called.  
  
 Finally, the code in this section uses a modified version of the GetNewConnection function. This version of the function now returns a client-side cursor. The function looks like this:  
  
```  
'BeginNewConnection  
Public Function GetNewConnection() As ADODB.Connection  
    On Error GoTo ErrHandler:  
  
    Dim objConn As New ADODB.Connection  
    Dim strConnStr As String  
  
    strConnStr = "Provider='SQLOLEDB';Initial Catalog='Northwind';" & _  
                 "Data Source='MySqlServer';Integrated Security='SSPI';"  
  
    objConn.ConnectionString = strConnStr  
    objConn.CursorLocation = adUseClient  
    objConn.Open  
  
    Set GetNewConnection = objConn  
  
    Exit Function  
  
ErrHandler:  
    Set objConn = Nothing  
    Set GetNewConnection = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Function  
'EndNewConnection  
```  
  
 This section contains the following topics.  
  
-   [Editing Existing Records](../../../ado/guide/data/editing-existing-records.md)  
  
-   [Adding Records](../../../ado/guide/data/adding-records.md)  
  
-   [Determining What is Supported](../../../ado/guide/data/determining-what-is-supported.md)  
  
-   [Deleting Records Using the Delete Method](../../../ado/guide/data/deleting-records-using-the-delete-method.md)  
  
-   [Alternatives: Using SQL Statements](../../../ado/guide/data/alternatives-using-sql-statements.md)
