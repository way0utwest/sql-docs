---
title: "Import Policies Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "database-engine"
ms.service: ""
ms.component: "performance-monitor"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.dmf.importpolicy.f1"
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
caps.latest.revision: 22
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Import Policies Dialog Box
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.  
  
## Options  
 **Files to import**  
 To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.  
  
 **Replace duplicates with items imported**  
 Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance. A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten. If this option is not selected, an existing condition that is using the same condition expression will not cause an error.  
  
 **Policy state**  
 Select the state that you want for the imported policy:  
  
-   **Preserve policy state on import**  
  
-   **Enable all policies on import**  
  
-   **Disable all policies on import**  
  
## See Also  
 [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)   
 [Import a Policy-Based Management Policy](../../relational-databases/policy-based-management/import-a-policy-based-management-policy.md)   
 [Export a Policy-Based Management Policy](../../relational-databases/policy-based-management/export-a-policy-based-management-policy.md)  
  
  
