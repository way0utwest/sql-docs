---
title: "Lesson 1: Creating a Sample Subscriber Database | Microsoft Docs"
ms.custom: ""
ms.date: "05/30/2017"
ms.prod: "reporting-services"
ms.prod_service: "reporting-services-native"
ms.service: ""
ms.component: "reporting-services"
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "SQL Server 2016"
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
caps.latest.revision: 45
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
ms.workload: "On Demand"
---

# Lesson 1: Creating a Sample Subscriber Database

In this [!INCLUDE[ssRSnoversion_md](../includes/ssrsnoversion-md.md)] tutorial lesson, you create a small "subscriber" database to store subscription data that will be used by a data-driven subscription. When the subscription is processed, the report server retrieves this data and uses it to customize report output. For example, the rows of data include specific order numbers to use for filters and what file format generated reports will be in when they are created.  
  
This lesson assumes you are using [!INCLUDE[ssManStudioFull_md](../includes/ssmanstudiofull-md.md)] to create a SQL Server database.  
  
### To create a sample Subscriber database  
  
1.  Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and open a connection to an instance of the [!INCLUDE[ssDEnoversion_md](../includes/ssdenoversion-md.md)].  
  
2.  Right-click on Databases, select **New Database...**.  
  
3.  In the New Database dialog box, in **Database Name**, type *Subscribers*. 
4. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  Click the **New Query** button on the toolbar.  
  
6.  Copy the following [!INCLUDE[tsql](../includes/tsql-md.md)] statements into the empty query:  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
7.  Click **! Execute** on the toolbar.  
  
8.  Use a SELECT statement to verify that you have three rows of data. For example: `select * from OrderInfo`  
  
## Next Steps  
+ You have successfully created the subscription data that will drive report distribution and vary the report output for each subscriber. 
+ Next, you will modify the data source properties of the report to use stored credentials. 
+ You will also modify the report design to include a parameter that the subscription will use with the subscriber data. [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md).  

## Next steps

[Create a Data-Driven Subscription](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md)  
[Create a Database](../relational-databases/databases/create-a-database.md)  
[Create a Basic Table Report](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)  

More questions? [Try asking the Reporting Services forum](http://go.microsoft.com/fwlink/?LinkId=620231)
