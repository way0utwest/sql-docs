---
title: "Analysis Services PowerShell Reference | Microsoft Docs"
ms.custom: ""
ms.date: "06/21/2017"
ms.prod: "analysis-services"
ms.prod_service: "analysis-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6c435e40-bfaf-4073-8cef-bc3260602246
caps.latest.revision: 9
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
ms.workload: "On Demand"
---
# Analysis Services PowerShell Reference
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]

  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets are included in the [SqlServer module](https://www.powershellgallery.com/packages/SqlServer/21.0.17099). 
  
>[!NOTE] 
> Azure Analysis Services database operations use the same SqlServer module as SQL Server Analysis Services. However, not all cmdlets are supported for Azure Analysis Services. To learn more, see [Manage Azure Analysis Services with PowerShell](https://docs.microsoft.com/azure/analysis-services/analysis-services-powershell).
  
##  <a name="bkmk_cmdlets"></a> Analysis Services Cmdlets  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides cmdlets correspond to methods in the **Microsoft.AnalysisServices** namespace. The following table describes each cmdlet and provides a link to the corresponding AMO method.  
  
 If you want to use PowerShell to perform a task that is not represented in the following list (for example to create or synchronize a database), you can write TMSL or XMLA script for that action, and then execute it using the **Invoke-ASCmd** cmdlet.  
  
|Cmdlet|Description|Equivalent AMO Methods|  
|------------|-----------------|----------------------------|  
|[Add-RoleMember cmdlet](../../analysis-services/powershell/add-rolemember-cmdlet.md)|Add a member to a database role.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Add%2A>|  
|[Backup-ASDatabase cmdlet](../../analysis-services/powershell/backup-asdatabase-cmdlet.md)|Backup an Analysis Services database.|[Database.Backup](https://msdn.microsoft.com/library/microsoft.analysisservices.database.backup.aspx)|  
|[Invoke-ASCmd cmdlet](../../analysis-services/powershell/invoke-ascmd-cmdlet.md)|Execute a query or script in XMLA or TSML (JSON) format.|<xref:Microsoft.AnalysisServices.Core.Server.Execute%2A>|  
|[Invoke-ProcessASDatabase](../../analysis-services/powershell/invoke-processasdatabase.md)|Process a database.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessCube cmdlet](../../analysis-services/powershell/invoke-processcube-cmdlet.md)|Process a cube.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessDimension cmdlet](../../analysis-services/powershell/invoke-processdimension-cmdlet.md)|Process a dimension.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessPartition cmdlet](../../analysis-services/powershell/invoke-processpartition-cmdlet.md)|Process a partition.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessTable cmdlet](../../analysis-services/powershell/invoke-processtable-cmdlet.md)|Process a table in a Tabular model, compatibility model 1200 or higher.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Merge-Partition cmdlet](../../analysis-services/powershell/merge-partition-cmdlet.md)|Merge a partition.|<xref:Microsoft.AnalysisServices.Partition.Merge%2A>|  
|[New-RestoreFolder cmdlet](../../analysis-services/powershell/new-restorefolder-cmdlet.md)|Create a folder to contain a database backup.|<xref:Microsoft.AnalysisServices.RestoreFolder>|  
|[New-RestoreLocation cmdlet](../../analysis-services/powershell/new-restorelocation-cmdlet.md)|Specify one or more remote servers on which to restore the database.|<xref:Microsoft.AnalysisServices.RestoreLocation>|  
|[Remove-RoleMember cmdlet](../../analysis-services/powershell/remove-rolemember-cmdlet.md)|Remove a member from a database role.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Remove%2A>|  
|[Restore-ASDatabase cmdlet](../../analysis-services/powershell/restore-asdatabase-cmdlet.md)|Restore a database on a server instance.|<xref:Microsoft.AnalysisServices.Core.Server.Restore%2A>|  
  

  
  
