---
title: "SQLPostInstallerError Function | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "odbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "SQLPostInstallerError"
apilocation: 
  - "sqlsrv32.dll"
apitype: "dllExport"
f1_keywords: 
  - "SQLPostInstallerError"
helpviewer_keywords: 
  - "SQLPostInstallerError function [ODBC]"
ms.assetid: 4c60d827-b2d2-4f27-b220-daa9e1fcdd8d
caps.latest.revision: 7
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLPostInstallerError Function
**Conformance**  
 Version Introduced: ODBC 3.0  
  
 **Summary**  
 **SQLPostInstallerError** provides a mechanism for a driver or translator setup library to report errors for the **ConfigDriver**, **ConfigDSN**, and **ConfigTranslator** functions to the installer error queue. Applications do not use this API; they use **SQLInstallerError** to retrieve the error.  
  
## Syntax  
  
```  
  
RETCODE SQLPostInstallerError(  
     DWORD    fErrorCode,  
     LPSTR    szErrorMsg);  
```  
  
## Arguments  
 *fErrorCode*  
 [Input] Installer error code.  
  
 *szErrorMsg*  
 [Input] Error message text.  
  
## Returns  
 SQL_SUCCESS or SQL_ERROR.  
  
## Diagnostics  
 **SQLPostInstallerError** does not post error values for itself. If the error was successfully posted to the installer error queue (retrievable using **SQLInstallerError**), SQL_SUCCESS is returned. SQL_ERROR will be returned if the value in the *dwErrorCode* argument is not one of the specified installer error codes.  
  
## Related Functions  
  
|For information about|See|  
|---------------------------|---------|  
|Adding, modifying, or removing a driver|[ConfigDriver](../../../odbc/reference/syntax/configdriver-function.md)|  
|Adding, modifying, or removing data sources|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md)|  
|Setting a translation option|[ConfigTranslator](../../../odbc/reference/syntax/configtranslator-function.md)|
