---
title: "Step 2: Initialize the Main List Box | Microsoft Docs"
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
ms.assetid: a1454493-1c86-46c2-ada8-d3c6fcdaf3c1
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Step 2: Initialize the Main List Box
To declare global Record and Recordset objects, insert the following code into the (General) (Declarations) for Form1:  
  
```  
Option Explicit  
Dim grec As Record  
Dim grs As Recordset  
```  
  
 This code declares global object references for Record and Recordset objects that will be used later in this scenario.  
  
## To connect to a URL and populate lstMain  
 Insert the following code into the Form Load event handler for Form1:  
  
```  
Private Sub Form_Load()  
    Set grec = New Record  
    Set grs = New Recordset  
    grec.Open "", "URL=http://servername/foldername/", , _  
        adOpenIfExists Or adCreateCollection  
    Set grs = grec.GetChildren  
    While Not grs.EOF  
        lstMain.AddItem grs(0)  
        grs.MoveNext  
    Wend  
End Sub  
```  
  
 This code instantiates the global Record and Recordset objects. The Record object, `grec`, is opened with a URL specified as the ActiveConnection. If the URL exists, it is opened; if it does not already exist, it is created. Note that you should replace "http://servername/foldername/" with a valid URL from your environment.  
  
 The Recordset object, `grs`, is opened on the children of the Record, `grec`. Then `lstMain` is populated with the file names of the resources published to the URL.  
  
## See Also  
 [Internet Publishing Scenario](../../../ado/guide/data/internet-publishing-scenario.md)   
 [Step 1: Set Up the Visual Basic Project](../../../ado/guide/data/step-1-set-up-the-visual-basic-project.md)   
 [Step 3: Populate the Fields List Box](../../../ado/guide/data/step-3-populate-the-fields-list-box.md)
