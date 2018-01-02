---
title: "SQLAllocEnv Mapping | Microsoft Docs"
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
helpviewer_keywords: 
  - "SQLAllocEnv function [ODBC], mapping"
  - "mapping deprecated functions [ODBC], SQLAllocEnv"
ms.assetid: 4bb51845-ee91-4b97-9dd4-2fab977f2aec
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLAllocEnv Mapping
When an application calls **SQLAllocEnv** through an ODBC 3*.x* driver, the call to **SQLAllocEnv**(*phenv*) is mapped to **SQLAllocHandle** as follows:  
  
1.  The Driver Manager allocates an environment handle and returns it to the application. The Driver Manager calls **SQLSetEnvAttr** to set the SQL_ATTR_ODBC_VERSION environment attribute to SQL_OV_ODBC2.  
  
2.  When the application establishes the first connection to a driver, the Driver Manager calls  
  
    ```  
    SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE, OutputHandlePtr)  
    ```  
  
     in the driver with *OutputHandlePtr* set to *phenv*.
