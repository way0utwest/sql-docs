---
title: "Report Viewer web part on a SharePoint site - SSRS | Microsoft Docs"
ms.custom: ""
ms.date: "09/25/2017"
ms.prod: "reporting-services"
ms.prod_service: "reporting-services-sharepoint, reporting-services-native"
ms.service: ""
ms.component: "report-server-sharepoint"
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
author: "guyinacube"
ms.author: "asaxton"
manager: "kfile"
ms.workload: "Inactive"
---
# Report Viewer web part on a SharePoint site - Reporting Services

[!INCLUDE[ssrs-appliesto](../../includes/ssrs-appliesto.md)] [!INCLUDE[ssrs-appliesto-2016-and-later](../../includes/ssrs-appliesto-2016-and-later.md)] [!INCLUDE[ssrs-appliesto-sharepoint-2013-2016i](../../includes/ssrs-appliesto-sharepoint-2013-2016.md)] [!INCLUDE[ssrs-appliesto-pbirsi](../../includes/ssrs-appliesto-pbirs.md)]

The Report Viewer web part is a custom web part. You can use the web part to view, navigate, print, and export reports on a report server within a SharePoint site. The Report Viewer web part is associated with report definition (.rdl) files that are processed by a Microsoft SQL Server Reporting Services report server. 

The latest Report Viewer web part can also service paginated reports deployed to Power BI Report Server. The web part does not work with Power BI reports.

## Why the Report Viewer web part is re-introduced

The Report Viewer web part was available as part of the Reporting Services Add-in for SharePoint products. The web part was specific for report servers in SharePoint integrated mode. SharePoint integrated mode was deprecated after SQL Server 2016.

Starting with SQL Server 2017, there’s only one installation mode for Reporting Services: **Native mode**. You could embed all reports types using a Page Viewer web part using the *rs:Embed=true* URL parameter. Embedding reports into SharePoint pages is an integration story requested by customers and the updated Report Viewer web part enables this scenario for paginated reports.

While the Page Viewer web part suffices to embed a paginated report into a SharePoint page, the updated Report Viewer web part offers additional features.

* Show/hide specific toolbar buttons
* Override report parameter values
* Connect Filter web parts to report parameters

## Download the Report Viewer web part solution package

The Report Viewer web part is available on the Microsoft Download Center.

[Download Report Viewer web part solution package](https://www.microsoft.com/download/details.aspx?id=55949)

## Considerations and limitations

The items listed are specific to the updated Report Viewer web part.

* The web part can only be used on *classic* SharePoint pages.
* Only paginated (RDL) reports are supported for embedding in the Report Viewer web part. If you are looking to embed Power BI reports or mobile reports, you can use the *rs:Embed=true* URL parameter.

## Next steps

To get started with the updated Report Viewer web part, see [Deploy the Report Viewer web part on a SharePoint site](deploy-report-viewer-web-part.md).
