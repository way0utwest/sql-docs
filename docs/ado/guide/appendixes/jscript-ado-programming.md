---
title: "JScript ADO Programming | Microsoft Docs"
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
dev_langs: 
  - "JScript"
helpviewer_keywords: 
  - "JScript programming in ADO"
  - "ADO, JScript programming"
ms.assetid: 62273658-0fe7-4aac-b4d8-f725e6baf043
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# JScript ADO Programming
## Creating an ADO Project  
 Microsoft JScript does not support type libraries, so you do not need to reference ADO in your project. Consequently, no associated features such as command line completion are supported. Also, by default, ADO enumerated constants are not defined in JScript.  
  
 However, ADO provides you with two include files containing the following definitions to be used with JScript:  
  
-   For server-side scripting use Adojavas.inc, which is installed in the ADO library folders.  
  
-   For client-side scripting use Adcjavas.inc, which is installed in the ADO library folders.  
  
 You can either copy and paste constant definitions from these files into your ASP pages, or, if you are doing server-side scripting, copy Adojavas.inc file to a folder on your Web site and references it from your ASP page like this:  
  
```  
<!--#include File="adojavas.inc"-->  
```  
  
## Creating ADO Objects in JScript  
 You must instead use the **CreateObject** function call:  
  
```  
var Rs1;  
Rs1 = Server.CreateObject("ADODB.Recordset");  
```  
  
## JScript Example  
 The following code is a generic example of JScript server-side programming in an Active Server Page (ASP) file that opens a **Recordset** object:  
  
```  
<%  @LANGUAGE="JScript" %>  
<!--#include File="adojavas.inc"-->  
<HTML>  
<BODY BGCOLOR="White" topmargin="10" leftmargin="10">  
<%  
var Source = "SELECT * FROM Authors";  
var Connect =  "Provider=sqloledb;Data Source=srv;" +  
    "Initial Catalog=Pubs;Integrated Security=SSPI;"  
var Rs1 = Server.CreateObject( "ADODB.Recordset.2.5" );  
Rs1.Open(Source,Connect,adOpenForwardOnly);  
Response.Write("Success!");  
%>  
</BODY>  
</HTML>  
```
