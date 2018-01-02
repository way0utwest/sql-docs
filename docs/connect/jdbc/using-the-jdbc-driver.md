---
title: "Using the JDBC Driver | Microsoft Docs"
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
ms.assetid: 6faaf05b-8b70-4ed2-9b44-eee5897f1cd0
caps.latest.revision: 54
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Active"
---
# Using the JDBC Driver
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  This section provides quick start instructions for making a simple connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] database by using the [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]. Before you connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] must first be installed on either your local computer or a server, and the JDBC driver must be installed on your local computer.  
  
## Choosing the Right JAR file  
 The Microsoft JDBC Driver 6.2 for SQL Server provides **mssql-jdbc-6.2.1.jre7.jar**, and **mssql-jdbc-6.2.1.jre8.jar** class library files to be used depending on your preferred Java Runtime Environment (JRE) settings.  
  
  The Microsoft JDBC Drivers 6.0 and 4.2 for SQL Server provide **sqljdbc41.jar**, and **sqljdbc42.jar** class library files to be used depending on your preferred Java Runtime Environment (JRE) settings.  
  
 The Microsoft JDBC Driver 4.1 for SQL Server provides the **sqljdbc41.jar** class library file to be used depending on your preferred Java Runtime Environment (JRE) settings.  
  
 The [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 4.0 provides **sqljdbc.jar** and **sqljdbc4.jar** class library files to be used depending on your preferred Java Runtime Environment (JRE) settings.  
  
 Your choice will also determine available features. For more information about which JAR file to choose, see [System Requirements for the JDBC Driver](../../connect/jdbc/system-requirements-for-the-jdbc-driver.md).  
  
## Setting the Classpath  
 The JDBC driver is not part of the Java SDK. If you want to use it, you must set the classpath to include the **sqljdbc.jar** file, **sqljdbc4.jar** file, the **sqljdbc41.jar** file, or the **sqljdbc42.jar** file. If using JDBC Driver 6.2, set the classpath to include the **mssql-jdbc-6.2.1.jre7.jar** or **mssql-jdbc-6.2.1.jre8.jar**. If the classpath is missing an entry, your application will throw the common "Class not found" exception.  
  
### For Microsoft JDBC Driver 6.2
 The **mssql-jdbc-6.2.1.jre7.jar** or **mssql-jdbc-6.2.1.jre8.jar** files are installed in the following location:  
  
 \<*installation directory*>\sqljdbc_\<*version*>\\<*language*>\mssql-jdbc-6.2.1.jre7.jar 
  
 \<*installation directory*>\sqljdbc_\<*version*>\\<*language*>\mssql-jdbc-6.2.1.jre8.jar
  
 The following is an example of the CLASSPATH statement that is used for a Windows application:  
  
 `CLASSPATH =.;C:\Program Files\Microsoft JDBC Driver 6.2 for SQL Server\sqljdbc_6.2\enu\mssql-jdbc-6.2.1.jre8.jar`  
  
 The following is an example of the CLASSPATH statement that is used for a Unix/Linux application:  
  
 `CLASSPATH =.:/home/usr1/mssqlserverjdbc/Driver/sqljdbc_6.2/enu/mssql-jdbc-6.2.1.jre8.jar`  
  
 You must make sure that the CLASSPATH statement contains only one [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], such as either mssql-jdbc-6.2.1.jre7.jar or mssql-jdbc-6.2.1.jre8.jar.  

### For Microsoft JDBC Driver 4.0, 4.1, 4.2, and 6.0
 The sqljdbc.jar file, sqljdbc4.jar file, sqljdbc41.jar, or sqljdbc42.jar file are installed in the following location:  
  
 \<*installation directory*>\sqljdbc_\<*version*>\\<*language*>\sqljdbc.jar  
  
 \<*installation directory*>\sqljdbc_\<*version*>\\<*language*>\sqljdbc4.jar  
  
 \<*installation directory*>\sqljdbc_\<*version*>\\<*language*>\sqljdbc41.jar  
  
 \<*installation directory*>\sqljdbc_\<*version*>\\<*language*>\sqljdbc42.jar  
  
 The following is an example of the CLASSPATH statement that is used for a Windows application:  
  
 `CLASSPATH =.;C:\Program Files\Microsoft JDBC Driver 6.0 for SQL Server\sqljdbc_4.2\enu\sqljdbc42.jar`  
  
 The following is an example of the CLASSPATH statement that is used for a Unix/Linux application:  
  
 `CLASSPATH =.:/home/usr1/mssqlserverjdbc/Driver/sqljdbc_4.2/enu/sqljdbc42.jar`  
  
 You must make sure that the CLASSPATH statement contains only one [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], such as either sqljdbc.jar, sqljdbc4.jar, sqljdbc41.jar, or sqljdbc42.jar.  
  
> [!NOTE]  
>  On Windows systems, directory names longer than the 8.3 filename convention or folder names with spaces may cause problems with classpaths. If you suspect these types of issues, you should temporarily move the sqljdbc.jar file, sqljdbc4.jar file, or the sqljdbc41.jar file into a simple directory name such as `C:\Temp`, change the classpath, and determine whether that addresses the problem.  
  
### Applications that are run directly at the command prompt  
 The classpath is configured in the operating system. Append sqljdbc.jar, sqljdbc4.jar, or sqljdbc41.jar to the classpath of the system. Alternatively, you can specify the classpath on the Java command line that runs the application by using the `java -classpath` option.  
  
### Applications that run in an IDE  
 Each IDE vendor provides a different method for setting the classpath in its IDE. Just setting the classpath in the operating system will not work. You must add sqljdbc.jar, sqljdbc4.jar, or sqljdbc41.jar to the IDE classpath.  
  
### Servlets and JSPs  
 Servlets and JSPs are run in a servlet/JSP engine such as Tomcat. The classpath must be set according to the servlet/JSP engine documentation. Just setting the classpath in the operating system will not work. Some servlet/JSP engines provide setup screens that you can use to set the classpath of the engine. In that situation, you must append the correct JDBC Driver JAR file to the existing engine classpath and restart the engine. In other situations, you can deploy the driver by copying sqljdbc.jar, sqljdbc4.jar, or sqljdbc41.jar to a specific directory, such as lib, during engine installation. The engine driver classpath can also be specified in an engine specific configuration file.  
  
### Enterprise Java Beans  
 Enterprise Java Beans (EJB) are run in an EJB container. EJB containers are sourced from various vendors. Java applets run in a browser but are downloaded from a web server. Copy sqljdbc.jar, sqljdbc4.jar, or sqljdbc41.jar to the web server root and specify the name of the JAR file in the HTML archive tab of the applet, for example, `<applet ... archive=sqljdbc.jar>`.  
  
## Making a Simple Connection to a Database  
 Using the sqljdbc.jar class library, applications must first register the driver as follows:  
  
 `Class.forName("com.microsoft.sqlserver.jdbc.SQLServerDriver");`  
  
 When the driver is loaded, you can establish a connection by using a connection URL and the getConnection method of the DriverManager class:  
  
```  
String connectionUrl = "jdbc:sqlserver://localhost:1433;" +  
   "databaseName=AdventureWorks;user=MyUserName;password=*****;";  
Connection con = DriverManager.getConnection(connectionUrl);  
```  
  
 In the JDBC API 4.0, the DriverManager.getConnection method is enhanced to load JDBC drivers automatically. Therefore, applications do not need to call the Class.forName method to register or load the driver when using the sqljdbc4.jar, sqljdbc41.jar, or sqljdbc42.jar class library.  
  
 When the getConnection method of the DriverManager class is called, an appropriate driver is located from the set of registered JDBC drivers. sqljdbc4.jar, sqljdbc41.jar, or sqljdbc42.jar file includes "META-INF/services/java.sql.Driver" file, which contains the **com.microsoft.sqlserver.jdbc.SQLServerDriver** as a registered driver. The existing applications, which currently load the drivers by using the Class.forName method, will continue to work without modification.  
  
> [!NOTE]  
>  sqljdbc4.jar, sqljdbc41.jar, or sqljdbc42.jar class library cannot be used with older versions of the Java Runtime Environment (JRE). See [System Requirements for the JDBC Driver](../../connect/jdbc/system-requirements-for-the-jdbc-driver.md) for the list of JRE versions supported by the [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)].  
  
 For more information about how to connect with data sources and use a connection URL, see [Building the Connection URL](../../connect/jdbc/building-the-connection-url.md) and [Setting the Connection Properties](../../connect/jdbc/setting-the-connection-properties.md).  
  
## See Also  
 [Overview of the JDBC Driver](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
  
  
