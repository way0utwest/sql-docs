---
title: "SMTP Connection Manager | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "connection-manager"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.smtpconnection.f1"
helpviewer_keywords: 
  - "connections [Integration Services], SMTP"
  - "SMTP connection manager [Integration Services]"
  - "connection managers [Integration Services], SMTP"
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
caps.latest.revision: 36
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "On Demand"
---
# SMTP Connection Manager
  An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server. The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.  
  
 When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication. Exchange servers may be configured to not allow unauthenticated SMTP connections.  
  
## Configuration the SMTP Connection Manager  
 When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the **Connections** collection on the package. The **ConnectionManagerType** property of the connection manager is set to **SMTP**.  
  
 You can configure an SMTP connection manager in the following ways:  
  
-   Provide a connection string.  
  
-   Specify the name of an SMTP server.  
  
-   Specify the authentication method to use.  
  
    > [!IMPORTANT]  
    >  The SMTP connection manager supports only anonymous authentication and Windows Authentication. It does not support basic authentication.  
  
-   Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.  
  
 You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.  
  
 For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../../integration-services/connection-manager/smtp-connection-manager-editor.md).  
  
 For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../../integration-services/building-packages-programmatically/adding-connections-programmatically.md).  
  
## SMTP Connection Manager Editor
  Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.  
  
 To learn more about the SMTP connection manager, see [SMTP Connection Manager](../../integration-services/connection-manager/smtp-connection-manager.md).  
  
### Options  
 **Name**  
 Provide a unique name for the connection manager.  
  
 **Description**  
 Describe the connection manager. As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.  
  
 **SMTP server**  
 Provide the name of the SMTP server.  
  
 **Use Windows Authentication**  
 Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.  
  
> [!IMPORTANT]  
>  The SMTP connection manager supports only anonymous authentication and Windows Authentication. It does not support basic authentication.  
  
> [!NOTE]  
>  When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to **True**. Exchange servers may be configured to disallow unauthenticated SMTP connections.  
  
 **Enable Secure Sockets Layer (SSL)**  
 Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.  
  
