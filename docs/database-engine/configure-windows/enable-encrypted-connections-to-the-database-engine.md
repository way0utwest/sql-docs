---
title: "Enable Encrypted Connections to the Database Engine | Microsoft Docs"
ms.custom: ""
ms.date: "12/21/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "configure-windows"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "connections [SQL Server], encrypted"
  - "SSL [SQL Server]"
  - "Secure Sockets Layer (SSL)"
  - "encryption [SQL Server], connections"
  - "cryptography [SQL Server], connections"
  - "certificates [SQL Server], installing"
  - "requesting encrypted connections"
  - "installing certificates"
  - "security [SQL Server], encryption"
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
caps.latest.revision: 48
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
ms.workload: "Active"
---
# Enable Encrypted Connections to the Database Engine
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager. The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority. Provisioning is the process of installing a certificate by importing it into Windows.  
  
 The certificate must be issued for **Server Authentication**. The name of the certificate must be the fully qualified domain name (FQDN) of the computer.  
  
 Certificates are stored locally for the users on the computer. To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager with an account that has local administrator privileges.
 
  
 The client must be able to verify the ownership of the certificate used by the server. If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary. [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows includes the public key certificates of many certification authorities. If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.  
  
> [!NOTE]  
>  To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster. For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes. You can set the value of the **ForceEncryption**option to **Yes**.  

> [!NOTE]
> When creating encrypted connections for an Azure Search indexer to SQL Server on an Azure VM, see [Configure a connection from an Azure Search indexer to SQL Server on an Azure VM](https://azure.microsoft.com/documentation/articles/search-howto-connecting-azure-sql-iaas-to-azure-search-using-indexers/). 
  
 
##  <a name="Provision"></a> To provision (install) a certificate on the server  
  
1.  On the **Start** menu, click **Run**, and in the **Open** box, type **MMC** and click **OK**.  
  
2.  In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.  
  
3.  In the **Add/Remove Snap-in** dialog box, click **Add**.  
  
4.  In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.  
  
5.  In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.  
  
6.  In the **Add Standalone Snap-in** dialog box, click **Close.**  
  
7.  In the **Add/Remove Snap-in** dialog box, click **OK**.  
  
8.  In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.  

9. Right-click the imported certificate, point to **All Tasks**, and then click **Manage Private Keys**. In the **Security** dialog box, add read permission for the user account used by the SQL Server service account.  
  
10. Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console. For more information about adding a certificate to a computer, see your Windows documentation.  
  
##  <a name="Export"></a> To export the server certificate  
  
1.  From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.  
  
2.  Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.  
  
##  <a name="ConfigureServerConnections"></a> To configure the server to force encrypted connections  
  
1.  In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** *\<server instance>*, and then select**Properties**.  
  
2.  In the **Protocols for** *\<instance name>* **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop-down for the **Certificate** box, and then click **OK**.  
  
3.  On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.  
  
4.  Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.  


> [!NOTE]
> To ensure secure connectivity between client and server, configure the client to request encrypted connections. More details are explained [later in this article](#client-request-encrypt-connect-23h).



### Wildcard Certificates  
Beginning with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support wildcard certificates. Other clients might not support wildcard certificates. For more information, see the client documentation. Wildcard certificate cannot be selected by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager. To use a wildcard certificate, you must edit the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQLServer\SuperSocketNetLib` registry key, and enter the thumbprint of the certificate, without spaces, to the **Certificate** value.  
> [!WARNING]  
> [!INCLUDE[ssnoteregistry_md](../../includes/ssnoteregistry_md.md)]  

<a name="client-request-encrypt-connect-23h"/>
##  <a name="ConfigureClientConnections"></a> To configure the client to request encrypted connections  
  
1.  Copy either the original certificate or the exported certificate file to the client computer.  
  
2.  On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.  
  
3.  In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.  
  
4.  On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.  
  
##  <a name="EncryptConnection"></a> To encrypt a connection from SQL Server Management Studio  
  
1.  On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.  
  
2.  In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.  
  
3.  On the **Connection Properties** tab, click **Encrypt connection**.  
  
## See Also

[TLS 1.2 support for Microsoft SQL Server](https://support.microsoft.com/kb/3135244)  

