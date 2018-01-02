---
title: "Alert Properties - New Alert (Response Page) | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "sql-tools"
ms.service: ""
ms.component: "ssms-agent"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "tools-ssms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.ag.alert.response.f1"
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Alert Properties - New Alert (Response Page)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
Use this page to specify a job that you want to run and to obtain a list of operators to be notified in response to a [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent alert.  
  
## Options  
**Execute job**  
Enables the **Job list**, **New job** and **View job** options.  
  
**New job**  
Open the **New Job** dialog box. This button is not available when **Execute job** is not selected.  
  
**View job**  
View or modify the selected job. This option is not available when **Execute job** is not selected.  
  
**Notify operators**  
Enables the controls that allow you to add, remove, or change operators.  
  
**Operator list**  
Lists the operators to notify when an alert occurs. To specify a notification method, select the **E-mail**, **Pager**, or **Net send** check box that is displayed after the operator name.This option not available when **Notify operators** is not selected.  
  
**E-mail**  
Use e-mail to notify the operator.  
  
**Pager**  
Use the pager e-mail address to notify the operator.  
  
**Net send**  
Use **net send** to notify the operator.  
  
**New operator**  
Displays the **New Operator** dialog box, which you can use to create a new operator.  
  
**View operator**  
Displays the **Properties** dialog box for the currently selected operator. You can view and modified operator properties on the the **Operator Properties** dialog box.  
  
## See Also  
[Alerts](../../ssms/agent/alerts.md)  
[Create an Alert Using Severity Level](../../ssms/agent/create-an-alert-using-severity-level.md)  
[Alerts](../../ssms/agent/alerts.md)  
[Edit an Alert](../../ssms/agent/edit-an-alert.md)  
[Delete an Alert](../../ssms/agent/delete-an-alert.md)  
  
