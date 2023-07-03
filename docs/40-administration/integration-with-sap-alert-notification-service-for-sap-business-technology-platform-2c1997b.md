<!-- loio2c1997b4ea224b16b0b39cdda08ab1dd -->

# Integration with SAP Alert Notification Service for SAP Business Technology Platform

You can set up the SAP Alert Notification service for SAP BTP to send notifications for changes in the SAP Task Center background job statuses.



<a name="loio2c1997b4ea224b16b0b39cdda08ab1dd__prereq_gx2_kg1_xmb"/>

## Prerequisites

You have done the initial setup and have an instance of the SAP Alert Notification service for SAP BTP service. For more information, see [Initial Setup](https://help.sap.com/viewer/5967a369d4b74f7a9c2b91f5df8e6ab6/Cloud/en-US/812b6e3ed8934648ad15780cd51721ef.html).



## Context

For more details about the SAP Task Center background job types and statuses, see [Monitoring](monitoring-9b30be7.md).



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* \> *New Destination*. In the *Destination Configuration* section, choose *Service Instance* and fill in the following information:


    <table>
    <tr>
    <th valign="top">

    Property


    
    </th>
    <th valign="top">

    Description


    
    </th>
    <th valign="top">

    Example or Value


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        *Service Instance*


    
    </td>
    <td valign="top">
    
        Choose your service instance for SAP Alert Notification service for SAP BTP.


    
    </td>
    <td valign="top">
    
         


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *Name*


    
    </td>
    <td valign="top">
    
        The name must be `Task_Center_notifications`.


    
    </td>
    <td valign="top">
    
        **Value**:

    `Task_Center_notifications`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *Description*


    
    </td>
    <td valign="top">
    
        \(Optional\) Add a description.


    
    </td>
    <td valign="top">
    
         


    
    </td>
    </tr>
    </table>
    
2.  Choose *Next* and save the destination.

3.  From your subaccount navigate to *Instances and Subscriptions* and choose the row of the *SAP Alert Notifications* instance.

4.  Choose *Manage Instance* in the view on the right to open the SAP Alert Notification service view in a new tab.

5.  Configure notifications for changes in the SAP Task Center background job statuses.

    To configure when and how to get notified about changes in the status of a background job, you must set at least one subscription, condition and action. For more information, see [Configuration Management Using the SAP BTP Cockpit](https://help.sap.com/viewer/522e38b6b52443a19fafbde9afaf257e/Cloud/en-US/033cbf7cfab2484abad90276d3d3e776.html?q=Configuration%20Management%20Using%20the%20SAP%20Cloud%20Platform%20Cockpit) and [Exporting or Importing Configurations](https://help.sap.com/viewer/5967a369d4b74f7a9c2b91f5df8e6ab6/Cloud/en-US/771da5b383ee4722afc4eb1f58aa4648.html).

    1.  In the alert notification user interface go to the *Subscriptions* tab and choose *Create*. Add a name of the subscription and choose *Create*.

    2.  Choose *Create Condition* and add *Connector* as name of the condition. Choose a condition that matches your requirements and choose *Create*.

        > ### Tip:  
        > Keep in mind that SAP Task Center sends the following information:
        > 
        > -   The *eventType* is the same as the name of the connector background job and could be *INITIAL*, *CONFIG*, *DELTA*, *META*, or *PUSH*. For more information about the types, see [Monitoring](monitoring-9b30be7.md).
        > 
        > -   The *severity* can be *WARNING*, *ERROR*, or *INFO* and is aligned to the job statuses: *WARNING*, *ERROR* or *OK*.
        > 
        > -   The value of the *resource.resourceName* is the `connectorId` of the respective connector.
        > 
        > -   The *resource.resourceType* is always `Connector`.
        > 
        > 
        > You can use this information to set up as many conditions as needed.

        Make sure you assign this condition to the subscription.

    3.  Create an action.

        Choose from the available options, add the required details and choose *Assign*.





<a name="loio2c1997b4ea224b16b0b39cdda08ab1dd__result_bmx_qcb_xmb"/>

## Results

Notifications are sent after the first execution of any of the connector background jobs or when the status of a connector job changes.

**Related Information**  


[SAP Alert Notification Service for SAP Business Technology Platform](https://help.sap.com/viewer/5967a369d4b74f7a9c2b91f5df8e6ab6/Cloud/en-US)

[Managing Subscriptions](https://help.sap.com/viewer/522e38b6b52443a19fafbde9afaf257e/Cloud/en-US/07fd21e170c7452482c3532c5521bb90.html)

[Managing Conditions](https://help.sap.com/viewer/522e38b6b52443a19fafbde9afaf257e/Cloud/en-US/35ca5de101fc4d5791cdbb2df15e9d9b.html)

[Managing Actions](https://help.sap.com/viewer/522e38b6b52443a19fafbde9afaf257e/Cloud/en-US/8a7e092eebc74b3ea01d506265e8c8f8.html)

