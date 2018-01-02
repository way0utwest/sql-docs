---
title: "SQLXML Interface | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "jdbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7c67be98-efb5-446c-a0e3-ee67c43cb170
caps.latest.revision: 19
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# SQLXML Interface
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  The JDBC driver provides support for the JDBC 4.0 API, which introduces the java.sql.SQLXML interface. The SQLXML interface defines methods to interact and manipulate XML data. The **SQLXML** data type maps to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]**xml** data type.  
  
 The SQLXML interface provides methods for accessing the XML value as a **String**, a **Reader** or **Writer**, or as a **Stream**. The XML value may also be accessed through a **Source** or set as a **Result**, which are used with XML Parser APIs such as Document Object Model (DOM), Simple API for XML (SAX), and Streaming API for XML (StAX), as well as with XSLT transforms and XPath.  
  
## Remarks  
 The following table describes the methods defined in the SQLXML interface:  
  
|Method Syntax|Method Description|  
|-------------------|------------------------|  
|[void free()](http://go.microsoft.com/fwlink/?LinkId=131685)|This method frees the SQLXML object and releases the resources that it holds.|  
|[InputStream getBinaryStream()](http://go.microsoft.com/fwlink/?LinkId=131754)|Returns an input stream to read data from the SQLXML.|  
|[Reader getCharacterStream()](http://go.microsoft.com/fwlink/?LinkId=131755)|Returns the **XML** data as a java.io.Reader object or as a stream of characters.|  
|[T extends Source T getSource(Class\<T> sourceClass)](http://go.microsoft.com/fwlink/?LinkId=131756)|Returns a **Source** for reading the **XML** value specified by this **SQLXML** object.<br /><br /> **Note:**  The getSource method supports the following sources: javax.xml.transform.dom.DOMSource, javax.xml.transform.sax.SAXSource, javax.xml.transform.stax.StAXSource, and java.io.InputStream.|  
|[String getString()](http://go.microsoft.com/fwlink/?LinkId=131757)|Returns a string representation of the **XML** value designated by this SQLXML object.|  
|[OutputStream setBinaryStream()](http://go.microsoft.com/fwlink/?LinkId=131758)|Retrieves a stream that can be used to write the **XML** value that this SQLXML object represents.|  
|[Writer setCharacterStream()](http://go.microsoft.com/fwlink/?LinkId=131759)|Returns a stream to be used to write the **XML** value that this SQLXML object represents.|  
|[T extends Result T setResult(Class\<T> resultClass)](http://go.microsoft.com/fwlink/?LinkId=131760)|Returns a **Result** for setting the **XML** value specified by this **SQLXML** object.<br /><br /> **Note:** The setResult method supports the following sources: javax.xml.transform.dom.DOMResult, javax.xml.transform.sax.SAXResult, javax.xml.transform.stax.StaxResult, and java.io.OutputStream.|  
|[void setString(String value)](http://go.microsoft.com/fwlink/?LinkId=131762)|Sets the XML value designated by this SQLXML object to the specified **String** representation.|  
  
 The applications can read and write XML values to or from an SQLXML object only once.  
  
 When the free() method is called, a SQLXML object becomes invalid and is neither readable nor writeable. If the application tries to invoke a method on that SQLXML object other than the free() method, an exception is thrown.  
  
 The SQLXML object becomes neither readable nor writable when the application calls any of the following getter methods: getSource, getCharacterStream, getBinaryStream, and getString.  
  
 The SQLXML object becomes neither writeable nor readable when the application calls any of the following setter methods: setResult, setCharacterStream, setBinaryStream, and setString.  
  
## See Also  
 [Supporting XML Data](../../connect/jdbc/supporting-xml-data.md)  
  
  
