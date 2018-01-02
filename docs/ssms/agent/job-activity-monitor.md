---
title: "Job Activity Monitor | Microsoft Docs"
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
  - "sql13.ag.jobactivitymonitor.alljobs.f1"
  - "SQL13.SWB.ACTIVITYMON.F1"
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
caps.latest.revision: 4
author: "stevestein"
ms.author: "sstein"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Job Activity Monitor
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent jobs. Click **Filter** to limit the jobs displayed. The **Agent Job Activity** grid is read-only. Click on the column headers to sort the grid. To modify a job, double-click the job to open the **Job Properties** dialog box. Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job. Click **Refresh** to update the grid with current information.  
  
## Options  
**Name**  
Name of the job.  
  
**Enabled**  
Whether the job is enabled (**yes**) or not enabled (**no**).  
  
**Status***  
Current status of the job.  
  
**Last Run Outcome**  
Job status when last run.  
  
**Last Run**  
Date and time job was last run using the local date and time of the server.  
  
**Next Run***  
Date and time the job is next scheduled to run using the local date and time of the server.  
  
**Category**  
The job category assigned to the job.  
  
**Runnable**  
**Yes** if the job can be run; **No** if the job cannot be run. A job is not runnable if it has no steps or if it has no target server.  
  
**Scheduled**  
**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.  
  
*Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] sysadmin fixed server role and the server administrators group can see values in this column. Members of the SQLAgentOperatorRole role cannot see values in this column.  
  
#### To open the Job Activity Monitor  
  
-   In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.  
  
## See Also  
[Monitor Job Activity](../../ssms/agent/monitor-job-activity.md)  
  
