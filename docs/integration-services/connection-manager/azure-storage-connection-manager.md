---
title: "Azure Storage Connection Manager | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
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
  - "sql13.dts.designer.afpstorageconn.f1"
  - "sql14.dts.designer.afpstorageconn.f1"
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
caps.latest.revision: 13
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Azure Storage Connection Manager
  The **Azure Storage connection manager** enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.  
   
 The **Azure Storage connection manager** is a component of the [SQL Server Integration Services (SSIS) Feature Pack for Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md). 
  
1.  In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.  
  
2.  In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.  
  
3.  If you selected **Use Azure account** option, do the following:  
  
    1.  Specify values for the **Storage account name** and **Account key** field. These values will be stored as sensitive data in SSIS package.  
  
    2.  Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.  
  
4.  Click **OK** to close the dialog box.  
  
5.  You can see the properties of the connection manager you created in the **Properties** window.  
  
  
