---
title: "Azure Feature Pack for Integration Services (SSIS) | Microsoft Docs"
ms.custom: ""
ms.date: "08/22/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "integration-services"
ms.service: ""
ms.component: "non-specific"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SQL13.SSIS.AZURE.F1"
  - "SQL14.SSIS.AZURE.F1"
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
caps.latest.revision: 19
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
ms.workload: "On Demand"
---
# Azure Feature Pack for Integration Services (SSIS)
SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.

[![Download SSIS Feature Pack for Azure](../analysis-services/media/download.png)](https://www.microsoft.com/download/details.aspx?id=54798) **Download**

- For SQL Server 2017 - [Microsoft SQL Server 2017 Integration Services Feature Pack for Azure](https://www.microsoft.com/download/details.aspx?id=54798)
- For SQL Server 2016 - [Microsoft SQL Server 2016 Integration Services Feature Pack for Azure](https://www.microsoft.com/download/details.aspx?id=49492)
- For SQL Server 2014 - [Microsoft SQL Server 2014 Integration Services Feature Pack for Azure](https://www.microsoft.com/download/details.aspx?id=47366)
- For SQL Server 2012 - [Microsoft SQL Server 2012 Integration Services Feature Pack for Azure](https://www.microsoft.com/download/details.aspx?id=47367)

## Components in the Feature Pack
-   Connection Managers

    -   [Azure Storage Connection Manager](../integration-services/connection-manager/azure-storage-connection-manager.md)

    -   [Azure Subscription Connection Manager](../integration-services/connection-manager/azure-subscription-connection-manager.md)
    
    -   [Azure Data Lake Store Connection Manager](../integration-services/connection-manager/azure-data-lake-store-connection-manager.md)
    
    -   [Azure Resource Manager Connection Manager](../integration-services/connection-manager/azure-resource-manager-connection-manager.md)
    
    -   [Azure HDInsight Connection Manager](../integration-services/connection-manager/azure-hdinsight-connection-manager.md)

-   Tasks

    -   [Azure Blob Upload Task](../integration-services/control-flow/azure-blob-upload-task.md)

    -   [Azure Blob Download Task](../integration-services/control-flow/azure-blob-download-task.md)

    -   [Azure HDInsight Hive Task](../integration-services/control-flow/azure-hdinsight-hive-task.md)

    -   [Azure HDInsight Pig Task](../integration-services/control-flow/azure-hdinsight-pig-task.md)

    -   [Azure HDInsight Create Cluster Task](../integration-services/control-flow/azure-hdinsight-create-cluster-task.md)

    -   [Azure HDInsight Delete Cluster Task](../integration-services/control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [Azure SQL DW Upload Task](../integration-services/control-flow/azure-sql-dw-upload-task.md)

    -   [Azure Data Lake Store File System Task](../integration-services/control-flow/azure-data-lake-store-file-system-task.md)

-   Data Flow Components

    -   [Azure Blob Source](../integration-services/data-flow/azure-blob-source.md)

    -   [Azure Blob Destination](../integration-services/data-flow/azure-blob-destination.md)
    
    -   [Azure Data Lake Store Source](../integration-services/data-flow/azure-data-lake-store-source.md)
    
    -   [Azure Data Lake Store Destination](../integration-services/data-flow/azure-data-lake-store-destination.md)

-   Azure Blob & ADLS File Enumerator. See [Foreach Loop Container](http://msdn.microsoft.com/library/95a19dde-61ca-4d9b-aa3d-131fa4264296)

## Download the Feature Pack
 Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.
 
- [SSIS Feature Pack for Azure](http://go.microsoft.com/fwlink/?LinkID=626967) for SQL Server 2016
- [SSIS Feature Pack for Azure](https://www.microsoft.com/download/details.aspx?id=54798) for [!INCLUDE[ssSQLv14_md](../includes/sssqlv14-md.md)]

## Prerequisites
 You must install the following prerequisites before installing this feature pack.

-   SQL Server Integration Services
-   .Net Framework 4.5

## Scenario: Processing big data
 Use Azure Connector to complete following big data processing work:

1.  Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.

2.  Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster. This step is optional if you want to use your own cluster.

3.  Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.

4.  Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.

5.  Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.

![SSIS-AzureConnector-BigDataScenario](../integration-services/media/ssis-azureconnector-bigdatascenario.png)
 
## Scenario: Managing data in the cloud
 Use the Azure Blob Destination in an SSIS package to write output data to Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.

![SSIS-AzureConnector-CloudArchive-1](../integration-services/media/ssis-azureconnector-cloudarchive-1.png)
 
 ![SSIS-AzureConnector-CloudArchive-2](../integration-services/media/ssis-azureconnector-cloudarchive-2.png)

 Use the Foreach Loop Container with the Azure Blob Enumerator to process data in multiple blob files.

![SSIS-AzureConnector-CloudArchive-3](../integration-services/media/ssis-azureconnector-cloudarchive-3.png)
  
