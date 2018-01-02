---
title: "SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "reporting-services"
ms.prod_service: "reporting-services-sharepoint, reporting-services-native"
ms.service: ""
ms.component: "wmi-provider-library-reference"
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)"
apilocation: 
  - "reportingservices.mof"
apitype: "MOFDef"
helpviewer_keywords: 
  - "SetSecureConnectionLevel method"
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
caps.latest.revision: 21
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
ms.workload: "Inactive"
---
# ConfigurationSetting Method - SetSecureConnectionLevel
  Sets the secure connection level of the report server.  
  
## Syntax  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## Parameters  
 *Level*  
 An integer value representing a secure connection level.  
  
 *HRESULT*  
 [out] Value indicating whether the call succeeded or failed.  
  
## Return Value  
 Returns an *HRESULT* indicating success or failure of the method call. A value of 0 indicates that the method call was successful. A non-zero value indicates that an error has occurred.  
  
## Remarks  
 When called, the report server SecureConnectionLevel property is set to the value specified. A value of 0 indicates that SSL is turned off. A value greater than or equal to 1 indicates that SSL is turned on.  
  
-   When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the **URLRoot** element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.  
  
 In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0. For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file. Values of 2 and 3 are still allowed for backward compatibility.  
  
## Requirements  
 **Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## See Also  
 [MSReportServer_ConfigurationSetting Members](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-members.md)  
  
  
