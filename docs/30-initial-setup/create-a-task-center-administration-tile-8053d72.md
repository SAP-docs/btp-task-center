<!-- loio8053d72535eb4c7891cfc0cf07104a8d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Administration Tile

Create a Task Center Administration tile in the central point of entry for accessing applications of your choice, to provide the opportunity to administrators to monitor the status of the SAP Task Center service and all active destinations, and get information about their jobs and job types.



<a name="loio8053d72535eb4c7891cfc0cf07104a8d__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

-   You have created the *Task\_Center* destination for the integration with your central point of entry for accessing applications. For more information, see [Destination for the Central Point of Entry for Accessing Applications](../40-administration/destination-for-the-central-point-of-entry-for-accessing-applications-10320af.md).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).

-   You have completed the onboarding process of your central point of entry for accessing applications, you have a subscription to it in your subaccount, and you have the required role collection assigned to your user.

    **Central Point of Entry for Accessing Applications - Onboarding Information**


    <table>
    <tr>
    <th valign="top">

    Central Point of Entry for Accessing Applications
    
    </th>
    <th valign="top">

    Onboarding Information
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, advanced edition
    
    </td>
    <td valign="top">
    
    Make sure you have completed the SAP Build Work Zone, advanced edition onboarding process and have the `Workzone_Admin` role collection assigned to your user. For more information, see [Onboarding to SAP Build Work Zone, advanced edition](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/onboarding-to-sap-build-work-zone-advanced-edition).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, standard edition
    
    </td>
    <td valign="top">
    
    Make sure you have completed the SAP Build Work Zone, standard edition initial setup and have the `Launchpad_Admin` role collection assigned to your user. For more information, see [Initial Setup](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/initial-setup).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP SuccessFactors Work Zone
    
    </td>
    <td valign="top">
    
    Make sure you have completed the SAP SuccessFactors Work Zone onboarding process and have the `HR_Workflow_Admin` role collection assigned to your user. For more information, see [Onboarding to SAP SuccessFactors Work Zone](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/edc62f97f50a432bb8dba04626689050.html).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Cloud Portal service
    
    </td>
    <td valign="top">
    
    Make sure you have complete the initial setup process. For more information, see [Initial Setup](https://help.sap.com/docs/cloud-portal-service/sap-cloud-portal-service-on-cloud-foundry/initial-setup).

    > ### Note:  
    > The SAP Cloud Portal service is not available in Service Marketplace in the SAP BTP cockpit. This integration is only relevant to existing subscriptions.


    
    </td>
    </tr>
    </table>
    



<a name="loio8053d72535eb4c7891cfc0cf07104a8d__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center Administration tile in the central point of entry for accessing applications. The Task Center Administration app displays the status of all active destinations, information about their jobs and job types. For more information about the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).



<a name="loio8053d72535eb4c7891cfc0cf07104a8d__steps_gwx_4ql_xbc"/>

## Procedure

1.  Create a **Task Center Administration** tile in the central point of entry for accessing applications of your choice.

    Follow the documentation of your central point of entry for accessing applications and add the **Task Center Administration** content item.

    **Creating a Tile in the Central Point of Entry for Accessing Applications**


    <table>
    <tr>
    <th valign="top">

    Central Point of Entry for Accessing Applications
    
    </th>
    <th valign="top">

    Link to Documentation
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, advanced edition
    
    </td>
    <td valign="top">
    
    [Create a Task Center Tile](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/create-task-center-tile)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, standard edition
    
    </td>
    <td valign="top">
    
    [Create a Task Center Tile](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/create-task-center-tile)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP SuccessFactors Work Zone
    
    </td>
    <td valign="top">
    
    [Create a Task Center Tile](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/create-task-center-tile)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Cloud Portal service
    
    </td>
    <td valign="top">
    
    [Create a Task Center Tile](https://help.sap.com/docs/cloud-portal-service/sap-cloud-portal-service-on-cloud-foundry/create-task-center-tile).
    
    </td>
    </tr>
    </table>
    
    > ### Caution:  
    > If you have already enabled SAP Companion for the SAP Task Center Web app used by end users, and you want to enable SAP Companion for the Task Center Administration app as well, we recommend you to create a new site for the Task Center Administration app, and then set up the SAP Companion for the Task Center Administration app.

2.  Activate the languages from the *Site Settings* tile to a new site. Currently you can set up only one SAP Companion to enable the available translations for the Web app. For more information about the supported languages, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

3.  \(Optional\) Activate the SAP Companion to enable on-screen help in the Task Center Administration app.

    For more information about the SAP Companion, see [SAP Enable Now](https://help.sap.com/viewer/product/SAP_ENABLE_NOW/latest/en-US?task=use_task).

    Note, that the SAP Companion content for the Task Center Administration app is currently only in English.

    Follow the steps:

    1.  From the *Site Directory*\(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\) open the *Site Settings*\(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).
    2.  Choose *Edit* and activate the *SAP Companion* setting by choosing *YES*.
    3.  Add the following parameters:


        <table>
        <tr>
        <th valign="top">

        Name
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        product
        
        </td>
        <td valign="top">
        
        TASK\_CENTER\_ADMIN
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        version
        
        </td>
        <td valign="top">
        
        Cloud
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        stateUACP
        
        </td>
        <td valign="top">
        
        PRODUCTION
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        dataUrlUACP
        
        </td>
        <td valign="top">
        
        https://help.sap.com/webassistant/
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        resourceUrl
        
        </td>
        <td valign="top">
        
        https://webassistant.enable-now.cloud.sap/web\_assistant/framework/
        
        </td>
        </tr>
        </table>
        
    4.  Save your site settings.

    > ### Restriction:  
    > Currently, only one SAP Companion per site is supported. For more information, see the restrictions of your central point of entry for accessing applications. For example, see [Restrictions](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/restrictions-general) for SAP Build Work Zone, standard edition.
    > 
    > To use SAP Companion in the Task Center Administration app, create a new site.




<a name="loio8053d72535eb4c7891cfc0cf07104a8d__result_h3j_4ss_tnb"/>

## Results

The integration of the Task Center Administration app in your central point of entry for accessing applications is done and the Task Center Administration tile is available to administrators. For more information about the details provided by the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).

Administrators can access the available on-screen help by choosing the SAP Companion icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the upper right corner of the Task Center Administration app.

