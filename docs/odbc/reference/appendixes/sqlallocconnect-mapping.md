---
title: "SQLAllocConnect Mapping | Microsoft Docs"
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
  - "SQLAllocConnect function [ODBC], mapping"
  - "mapping deprecated functions [ODBC], SQLAllocConnect"
ms.assetid: ac89dd1f-c565-47cc-8fa3-6fa5f80b5d63
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLAllocConnect Mapping
When an application calls **SQLAllocConnect** through an ODBC 3.*x* driver, the call to **SQLAllocConnect**(*henv*, *phdbc*) is mapped to **SQLAllocHandle** as follows:  
  
1.  The Driver Manager allocates a connection and returns it to the application.  
  
2.  When the application establishes a connection, the Driver Manager calls  
  
    ```  
    SQLAllocHandle(SQL_HANDLE_DBC, InputHandle, OutputHandlePtr)  
    ```  
  
     in the driver with *InputHandle* set to *henv*, and *OutputHandlePtr* set to *phdbc*.
