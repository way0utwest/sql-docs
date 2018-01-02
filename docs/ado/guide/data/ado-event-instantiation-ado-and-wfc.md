---
title: "ADO Event Instantiation: ADO and WFC | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "ado"
ms.technology:
  - "drivers"
ms.custom: ""
ms.date: "02/15/2017"
ms.reviewer: ""
ms.suite: "sql"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ee4be21-657b-407a-afa4-0b27a6b096ce
caps.latest.revision: 10
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# ADO Event Instantiation: ADO and WFC
ADO for Windows Foundation Classes (ADO/WFC) builds on the ADO event model and presents a simplified application programming interface. In general, ADO/WFC intercepts ADO events, consolidates the event parameters into a single event class, and then calls your event handler.  
  
### To use ADO events in ADO/WFC  
  
1.  Define your own event handler to process an event. For example, if you wanted to process the **ConnectComplete** event in the **ConnectionEvent** family, you might use this code:  
  
    ```  
    public void onConnectComplete(Object sender,ConnectionEvent e)  
    {  
        System.out.println("onConnectComplete:" + e);  
    }  
    ```  
  
2.  Define a handler object to represent your event handler. The handler object should be of data type **ConnectEventHandler** for an event of type **ConnectionEvent**, or data type **RecordsetEventHandler** for an event of type **RecordsetEvent**. For example, code the following for your **ConnectComplete** event handler:  
  
    ```  
    ConnectionEventHandler handler =   
        new ConnectionEventHandler(this, "onConnectComplete");  
    ```  
  
     The first argument of the **ConnectionEventHandler** constructor is a reference to the class that contains the event handler named in the second argument.  
  
3.  Add your event handler to a list of handlers designated to process a particular type of event. Use the method with a name such as **addOn***EventName*(*handler*).  
  
4.  ADO/WFC internally implements all the ADO event handlers. Therefore, an event caused by a **Connection** or **Recordset** operation is intercepted by an ADO/WFC event handler.  
  
     The ADO/WFC event handler passes ADO **ConnectionEvent** parameters in an instance of the ADO/WFC **ConnectionEvent** class, or ADO **RecordsetEvent** parameters in an instance of the ADO/WFC **RecordsetEvent** class. These ADO/WFC classes consolidate the ADO event parameters; that is, each ADO/WFC class contains one data member for each unique parameter in all the ADO **ConnectionEvent** or **RecordsetEvent** methods.  
  
5.  ADO/WFC then calls your event handler with the ADO/WFC event object. For example, your **onConnectComplete** handler has a signature like this:  
  
    ```  
    public void onConnectComplete(Object sender,ConnectionEvent e)  
    ```  
  
     The first argument is the type of object that sent the event ([Connection](../../../ado/reference/ado-api/connection-object-ado.md) or [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md)), and the second argument is the ADO/WFC event object (**ConnectionEvent** or **RecordsetEvent**).  
  
     The signature of your event handler is simpler than an ADO event. However, you must still understand the ADO event model to know what parameters apply to an event and how to respond.  
  
6.  Return from your event handler to the ADO/WFC handler for the ADO event. ADO/WFC copies pertinent ADO/WFC event data members back to the ADO event parameters, and then the ADO event handler returns.  
  
7.  When you are finished processing, remove your handler from the list of ADO/WFC event handlers. Use the method with a name such as **removeOn***EventName*(*handler*).  
  
## See Also  
 [ADO Event Handler Summary](../../../ado/guide/data/ado-event-handler-summary.md)   
 [ADO - WFC Syntax Index](../../../ado/reference/ado-api/ado-wfc-syntax-index.md)   
 [Event Parameters](../../../ado/guide/data/event-parameters.md)   
 [How Event Handlers Work Together](../../../ado/guide/data/how-event-handlers-work-together.md)   
 [Types of Events](../../../ado/guide/data/types-of-events.md)
