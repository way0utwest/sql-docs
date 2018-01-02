---
title: Encrypting Connections to SQL Server on Linux | Microsoft Docs
description: This topic describes Encrypting Connections to SQL Server on Linux.
author: tmullaney 
ms.date: 10/02/2017
ms.author: meetb;rickbyh 
manager: jhubbard
ms.topic: article
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: sql-linux
ms.suite: "sql"
ms.custom: ""
ms.technology: database-engine
ms.assetid: 
helpviewer_keywords: 
  - "Linux, encrypted connections"
ms.workload: "Inactive"
---
# Encrypting Connections to SQL Server on Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux can use Transport Layer Security (TLS) to encrypt data that is transmitted across a network between a client application and an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] supports the same TLS protocols on both Windows and Linux: TLS 1.2, 1.1, and 1.0. However, the steps to configure TLS are specific to the operating system on which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running.  

## Requirements for Certificates 
Before we get started, you need to make sure your certificates follow these requirements:
- The current system time must be after the Valid from property of the certificate and before the Valid to property of the certificate.
- The certificate must be meant for server authentication. This requires the Enhanced Key Usage property of the certificate to specify Server Authentication (1.3.6.1.5.5.7.3.1).
- The certificate must be created by using the KeySpec option of AT_KEYEXCHANGE. Usually, the certificate's key usage property (KEY_USAGE) will also include key encipherment (CERT_KEY_ENCIPHERMENT_KEY_USAGE).
- The Subject property of the certificate must indicate that the common name (CN) is the same as the host name or fully qualified domain name (FQDN) of the server computer. Note: Wild Card Certificates are supported. 

## Overview
TLS is used to encrypt connections from a client application to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. When configured correctly, TLS provides both privacy and data integrity for communications between the client and the server.  TLS connections can either be client intiated or server initited. 


## Client Initiated Encryption 
- **Generate certificate** (/CN should match your SQL Server host fully-qualified domain name)

> [!NOTE]
> For this example we use a Self-Signed Certificate, this should not be used for production scenarios. You should use CA certificates. 

        openssl req -x509 -nodes -newkey rsa:2048 -subj '/CN=mssql.contoso.com' -keyout mssql.key -out mssql.pem -days 365 
        sudo chown mssql:mssql mssql.pem mssql.key 
        sudo chmod 600 mssql.pem mssql.key   
        sudo mv mssql.pem /etc/ssl/certs/ 
        sudo mv mssql.key /etc/ssl/private/ 

- **Configure SQL Server**

        systemctl stop mssql-server 
        cat /var/opt/mssql/mssql.conf 
        sudo /opt/mssql/bin/mssql-conf set network.tlscert /etc/ssl/certs/mssqlfqdn.pem 
        sudo /opt/mssql/bin/mssql-conf set network.tlskey /etc/ssl/private/mssqlfqdn.key 
        sudo /opt/mssql/bin/mssql-conf set network.tlsprotocols 1.2 
        sudo /opt/mssql/bin/mssql-conf set network.forceencryption 0 

- **Register the certificate on your client machine (Windows, Linux or macOS)**

    -   If you are using CA signed certificate you have to copy the Certificate Authority (CA) certificate instead of the user certificate to the client machine. 
    -   If you are using the self-signed certificate just copy the .pem file to the following folders respective to distribution and execute the commands to enable them 
        - **Ubuntu** : Copy cert to ```/usr/share/ca-certificates/```  rename extension to .crt  use dpkg-reconfigure ca-certificates to enable it as system CA certificate. 
        - **RHEL** : Copy cert to ```/etc/pki/ca-trust/source/anchors/``` use ```update-ca-trust``` to enable it as system CA certificate.
        - **SUSE** : Copy cert to ```/usr/share/pki/trust/anchors/``` use ```update-ca-certificates``` to enable its as system CA certificate.
        - **Windows**:  Import the .pem file as a certificate under current user -> trusted root certification authorities -> certificates
        - **macOS**: 
           - Copy the cert to ```/usr/local/etc/openssl/certs```
           - Run the following command to get the hash value: ```/usr/local/Cellar/openssql/1.0.2l/openssql x509 -hash -in mssql.pem -noout```
           - Rename the cert to value. For example: ```mv mssql.pem dc2dd900.0```. Make sure dc2dd900.0 is in ```/usr/local/etc/openssl/certs```
    
-	**Example connection strings** 

    - **[!INCLUDE[ssmanstudiofull-md](../includes/ssmanstudiofull-md.md)]**   
  ![SSMS connection dialog](media/sql-server-linux-encrypted-connections/ssms-encrypt-connection.png "SSMS connection dialog")  
  
    - **SQLCMD** 

            sqlcmd  -S <sqlhostname> -N -U sa -P '<YourPassword>' 
    - **ADO.NET** 

            "Encrypt=True; TrustServerCertificate=False;" 
    - **ODBC** 

            "Encrypt=Yes; TrustServerCertificate=no;" 
    - **JDBC** 
    
            "encrypt=true; trustServerCertificate=false;" 

## Server Initiated Encryption 

- **Generate certificate** (/CN should match your SQL Server host fully-qualified domain name)
        
        openssl req -x509 -nodes -newkey rsa:2048 -subj '/CN=mssql.contoso.com' -keyout mssql.key -out mssql.pem -days 365 
        sudo chown mssql:mssql mssql.pem mssql.key 
        sudo chmod 600 mssql.pem mssql.key   
        sudo mv mssql.pem /etc/ssl/certs/ 
        sudo mv mssql.key /etc/ssl/private/ 

- **Configure SQL Server**

        systemctl stop mssql-server 
        cat /var/opt/mssql/mssql.conf 
        sudo /opt/mssql/bin/mssql-conf set network.tlscert /etc/ssl/certs/mssqlfqdn.pem 
        sudo /opt/mssql/bin/mssql-conf set network.tlskey /etc/ssl/private/mssqlfqdn.key 
        sudo /opt/mssql/bin/mssql-conf set network.tlsprotocols 1.2 
        sudo /opt/mssql/bin/mssql-conf set network.forceencryption 1 
        
-	**Example connection strings** 

    - **SQLCMD**

            sqlcmd  -S <sqlhostname> -U sa -P '<YourPassword>' 
    - **ADO.NET** 

            "Encrypt=False; TrustServerCertificate=False;" 
    - **ODBC** 

            "Encrypt=no; TrustServerCertificate=no;"  
    - **JDBC** 
    
            "encrypt=false; trustServerCertificate=false;" 
            
> [!NOTE]
> Set **TrustServerCertificate** to True if the client cannot connect to CA to validate the authenticity of the cert

## Common connection errors  

|Error message |Fix |
|--- |--- |
|The certificate chain was issued by an authority that is not trusted.  |This error occurs when clients are unable to verify the signature on the certificate presented by SQL Server during the TLS handshake. Make sure the client trusts either the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] certificate directly, or the CA which signed the SQL Server certificate. |
|The target principal name is incorrect.  |Make sure that Common Name field on SQL Server's certificate matches the server name specified in the client's connection string. |  
|An existing connection was forcibly closed by the remote host. |This error can occur when the client doesn't support the TLS protocol version required by SQL Server. For example, if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is configured to require TLS 1.2, make sure your clients also support the TLS 1.2 protocol. |
| | |   
