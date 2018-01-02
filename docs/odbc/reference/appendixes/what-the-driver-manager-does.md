---
title: "What the Driver Manager Does | Microsoft Docs"
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
  - "driver manager [ODBC], backward compatibility"
  - "compatibility [ODBC], driver manager"
  - "ODBC driver manager [ODBC]"
  - "backward compatibility [ODBC], driver manager"
ms.assetid: 57f65c38-d9ee-46c8-9051-128224a582c6
caps.latest.revision: 5
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# What the Driver Manager Does
The following table summarizes how the ODBC 3*.x* Driver Manager maps calls to ODBC 2.*x* and ODBC 3*.x* drivers.  
  
|Function or<br /><br /> statement attribute|Comments|  
|-----------------------------------------|--------------|  
|SQL_ATTR_FETCH_BOOKMARK_PTR|Points to the bookmark to use with **SQLFetchScroll**. The following are implementation details:<br /><br /> -   When an application sets this in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager caches it. It dereferences the pointer and passes the value to the ODBC 2.*x* driver in the *FetchOffset* argument of **SQLExtendedFetch** when **SQLFetchScroll** is later called by the application.<br />-   When an application sets this in an ODBC 3*.x* driver, the ODBC 3*.x* Driver Manager passes the call to the driver.|  
|SQL_ATTR_ROW_STATUS_PTR|Points to the row status array filled by **SQLFetch**, **SQLFetchScroll**, **SQLBulkOperations**, and **SQLSetPos**. The following are implementation details:<br /><br /> -   When an application sets this in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager caches its value. It passes this value to the ODBC 2.*x* driver in the *RowStatusArray* argument of **SQLExtendedFetch** when **SQLFetchScroll** or **SQLFetch** is called.<br />-   When an application sets this in an ODBC 3*.x* driver, the ODBC 3*.x* Driver Manager passes the call to the driver.<br />-   In state S6, if an application sets SQL_ATTR_ROW_STATUS_PTR and then calls **SQLBulkOperations** (with an *Operation* of SQL_ADD) or **SQLSetPos** without first calling **SQLFetch** or **SQLFetchScroll**, SQLSTATE HY011 (Attribute cannot be set now) is returned.|  
|SQL_ATTR_ROWS_FETCHED_PTR|Points to the buffer in which **SQLFetch** and **SQLFetchScroll** return the number of rows fetched. The following are implementation details:<br /><br /> -   When an application sets this in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager caches its value. It passes this value to the ODBC 2.*x* driver in the *RowCountPtr* argument of **SQLExtendedFetch** when **SQLFetch** or **SQLFetchScroll** is called by the application.<br />-   When an application sets this in an ODBC 3*.x* driver, the ODBC 3*.x* Driver Manager passes the call to the driver.|  
|SQL_ATTR_ROW_ARRAY_SIZE|Sets the rowset size. The following are implementation details:<br /><br /> -   When an application sets this in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager maps it to the SQL_ROWSET_SIZE statement attribute.<br />-   When an application sets this in an ODBC 3*.x* driver, the ODBC 3*.x* Driver Manager passes the call to the driver.<br />-   When an application working with an ODBC 3*.x* driver calls **SQLSetScrollOptions**, SQL_ROWSET_SIZE is set to the value in the *RowsetSize* argument if the underlying driver does not support **SQLSetScrollOptions**.|  
|SQL_ROWSET_SIZE|Sets the rowset size used by **SQLExtendedFetch** when **SQLExtendedFetch** is called by an ODBC 2*.x* application. The following are implementation details:<br /><br /> -   When an application sets this, the ODBC 3*.x* Driver Manager passes the call to the driver, regardless of driver version.<br />-   When an application working with an ODBC 2.*x* driver calls **SQLSetScrollOptions**, SQL_ROWSET_SIZE is set to the value in the **RowsetSize** argument.|  
|**SQLBulkOperations**|Performs an insert operation, or update, delete, or fetch by bookmark operations. The following are implementation details:<br /><br /> -   When an application calls **SQLBulkOperations** with an *Operation* of SQL_ADD in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager maps it to **SQLSetPos** with an *Operation* of SQL_ADD.<br />-   When working with an ODBC 2.*x* driver that does not support **SQLSetPos** with an *Operation* of SQL_ADD, the ODBC 3*.x* Driver Manager does not map **SQLSetPos** with an *Operation* of SQL_ADD to **SQLBulkOperations** with an *Operation* of SQL_ADD. This is because **SQLBulkOperations** cannot be called in state S7, which in ODBC 2.*x* was the only state in which **SQLSetPos** could be called.<br />-   If the application calls **SQLBulkOperations** with an *Operation* of SQL_ADD in an ODBC 2.*x* driver before calling **SQLFetchScroll**, the ODBC 3*.x* Driver Manager returns an error.|  
|**SQLExtendedFetch**|Returns the specified rowset. Except for the restriction just noted, the ODBC 3*.x* Driver Manager passes calls to **SQLExtendedFetch** to the driver, regardless of the driver version.|  
|**SQLFetch**|Returns the next rowset. The following are implementation details:<br /><br /> -   When an application calls **SQLFetch** in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager maps it to **SQLExtendedFetch**. The *FetchOrientation* argument of **SQLExtendedFetch** is set to SQL_FETCH_NEXT. The Driver Manager uses the cached value of the SQL_ATTR_ROW_STATUS_PTR statement attribute for the *RowStatusArray* argument and the cached value of the SQL_ATTR_ROWS_FETCHED_PTR statement attribute for the *RowCountPtr* argument.<br />-   An ODBC 3*.x* application can mix calls to **SQLFetch** and **SQLFetchScroll** in an ODBC 2.*x* driver because the ODBC 3*.x* Driver Manager maps **SQLFetch** to **SQLExtendedFetch** when an application calls it in an ODBC 2.*x* driver.<br />-   If an ODBC 2.*x* driver does not support **SQLExtendedFetch**, the ODBC 3*.x* Driver Manager does not map **SQLFetch** or **SQLFetchScroll** to **SQLExtendedFetch** when an application calls it in that driver. If the application attempts to set SQL_ATTR_ROW_ARRAY_SIZE to a value greater than 1, SQLSTATE HYC00 (Optional feature not implemented) is returned.<br />-   Except for the restrictions just noted, the ODBC 3*.x* Driver Manager passes calls to **SQLFetch** to the driver, regardless of the driver version.|  
|**SQLFetchScroll**|Returns the specified rowset. The following are implementation details:<br /><br /> -   When an application calls **SQLFetchScroll** in an ODBC 2.*x* driver, the ODBC 3*.x* Driver Manager maps it to **SQLExtendedFetch**. It uses the cached value of the SQL_ATTR_ROW_STATUS_PTR statement attribute for the *RowStatusArray* argument and the cached value of the SQL_ATTR_ROWS_FETCHED_PTR statement attribute for the *RowCountPtr* argument. If the *FetchOrientation* argument in **SQLFetchScroll** is SQL_FETCH_BOOKMARK, it uses the cached value of the SQL_ATTR_FETCH_BOOKMARK_PTR statement attribute for the *FetchOffset* argument and returns an error if the *FetchOffset* argument of **SQLFetchScroll** is not 0.<br />-   When an application calls this in an ODBC 3*.x* driver, the ODBC 3*.x* Driver Manager passes the call to the driver.|  
|**SQLSetPos**|Performs various positioned operations. The ODBC 3*.x* Driver Manager passes calls to **SQLSetPos** to the driver, regardless of the driver version.|  
|**SQLSetScrollOptions**|When the Driver Manager maps **SQLSetScrollOptions** for an application working with an ODBC 3*.x* driver that does not support **SQLSetScrollOptions**, the Driver Manager sets the SQL_ROWSET_SIZE statement option, not the SQL_ATTR_ROW_ARRAY_SIZE statement attribute, to the *RowsetSize* argument in **SQLSetScrollOption**. As a result, **SQLSetScrollOptions** cannot be used by an application when fetching multiple rows by a call to **SQLFetch** or **SQLFetchScroll**. It can be used only when fetching multiple rows by a call to **SQLExtendedFetch**.|
