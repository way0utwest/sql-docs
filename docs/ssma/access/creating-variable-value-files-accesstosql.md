---
title: "Creating Variable Value Files (AccessToSQL) | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssma-access"
ms.custom: ""
ms.date: "08/17/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "sql-ssma"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Azure SQL Database"
  - "SQL Server"
ms.assetid: 808595c3-8ef1-40bd-a93e-5cf237950e08
caps.latest.revision: 15
author: "Shamikg"
ms.author: "Shamikg"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Creating Variable Value Files (AccessToSQL)
A Variable Value File is an XML file comprising the parameter values of commands (such as the source or destination server name) that frequently change across server migrations. When a large number of database migrations occur, multiple variable files for storing the value of each source server are created and referenced in a master script file with the **–v** switch at command line. This behavior helps in maintaining static values in a few script files with the variable values in multiple variable files.  
  
> [!NOTE]  
> -  Variable names are prefixed and suffixed with a $ (dollar) symbol. If a variable is not assigned a value in the variable value file, an error during the parsing of the script file will occur, resulting in stalling the console execution process.  
> -  The escape character for **$** is **$$**. If the value of a variable or static value of a parameter contains a **$** (dollar) symbol, then **$$** must be specified to treat it as a character instead of a variable.  
> -  For maintainability purposes, variables can be declared inside `‘variable-group’` elements for logical separation of user-defined variables.  Usage of this element is not mandatory.  
  
**Examples:**  
  
**Example 1:**  
  
```xml  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="ProjectSpecs">  
  
    <variable name="$type$" value="MyProject"/>  
  
    <variable name="$project_folder$" value=".\$project_name$"/>  
  
    <variable name="$project_name$" value="$type$ConsoleProject"/>  
  
    <variable name="$project_overwrite$" value="true"/>  
  
    <variable name="$project_type$" value="sql-server-2008"/>  
  
  </variable-group>  
  
</variables>  
```  
**Example 2:**  
  
```xml  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="SQLServerParams">  
  
    <variable-group name="SqlServerConnectionParams">  
  
      <variable name="$TargetServerName$" value="xxx"/>  
  
      <variable name="$TargetDB$" value="xxx"/>  
  
      <variable name="$TargetUserName$" value="xxx"/>  
  
      <variable name="$TargetPassword$" value="xxx"/>  
  
      <variable name="$TargetIsTrusted$" value="xxx"/>  
  
      <variable name="$TrustedConnection$" value="xxx"/>  
  
    </variable-group>  
  
    <variable-group name="SqlServerObjectParams">  
  
      <variable name="$ObjectName1$" value="TestTable1"/>  
  
      <variable name="$ObjectName2$" value="TestProc1"/>  
  
    </variable-group>  
  
  </variable-group>  
  
</variables>  
```  
  
## Variable value file validation  
The user can easily validate his/her variable value file against the schema definition file **ConsoleScriptVariablesSchema.xsd** available in the ‘Schemas’ folder.  
  
## Next step  
The next step in operating the console is [Creating the Server Connection Files &#40;AccessToSQL&#41;](../../ssma/access/creating-the-server-connection-files-accesstosql.md)  
  
## See also  
[Creating the Server Connection Files (Access)](http://msdn.microsoft.com/829153be-aa8e-4162-87e8-69882feecf19)  
  
