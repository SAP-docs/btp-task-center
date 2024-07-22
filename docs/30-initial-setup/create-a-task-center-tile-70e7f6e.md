<!-- loio70e7f6e91e7b480796c5d24c34e1228e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Tile

Create a Task Center tile on SAP Build Work Zone, advanced edition, SAP Build Work Zone, standard edition \(formerly known as SAP Launchpad service\), SAP SuccessFactors Work Zone or SAP Cloud Portal service, depending on your central point of entry for accessing applications.



<a name="loio70e7f6e91e7b480796c5d24c34e1228e__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

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
    



<a name="loio70e7f6e91e7b480796c5d24c34e1228e__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center tile in your central point of entry for accessing applications. The Task Center tile opens the SAP Task Center Web app, which displays all tasks coming from the online connectors that are relevant for the logged-in user. For more information about the Web app, see [Using SAP Task Center](../70-using-the-web-app/using-sap-task-center-7de5ff4.md).



<a name="loio70e7f6e91e7b480796c5d24c34e1228e__steps_gwx_4ql_xbc"/>

## Procedure

1.  Make sure that you have the *Task\_Center* destination for the integration with your central point of entry for accessing applications. For more information, see [Destination for the Central Point of Entry for Accessing Applications](../40-administration/destination-for-the-central-point-of-entry-for-accessing-applications-10320af.md).

    > ### Caution:  
    > If you have followed the [Automatic Setup](automatic-setup-3a49967.md), this destination is already created by the booster. Please do not change this destination, and do not create a second destination for the central point of entry for accessing applications.

2.  Create a **Task Center** tile in the central point of entry for accessing applications of your choice.

    Follow the documentation of your central point of entry for accessing applications to add the **Task Center** tile and access the SAP Task Center Web app.

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
    
    [Create a Task Center Tile](https://help.sap.com/docs/cloud-portal-service/sap-cloud-portal-service-on-cloud-foundry/create-task-center-tile)
    
    </td>
    </tr>
    </table>
    
3.  Activate the languages from the *Site Settings* to enable the available translations for the Web app. For more information about the supported languages, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

4.  \(Optional\) Set up SAP Companion for the SAP Task Center Web app to enable the on-screen help for end users.

    Make sure you follow the documentation of your central point of entry for accessing applications and add the following parameters in the *Site Settings*:

    > ### Note:  
    > Note, that you can't run both the SAP Companion for SAP Task Center and SAP Companion for your central point of entry for accessing applications in parallel. You can set up only one of them. For more information, see the restrictions of your central poin of entry for accessing applications. For example, see [Restrictions](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/restrictions-general) for SAP Build Work Zone, standard edition.


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
    
    TASK\_CENTER
    
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
    



<a name="loio70e7f6e91e7b480796c5d24c34e1228e__result_xqn_jpz_xbc"/>

## Results

Once you complete this setup, the Task Center tile should be available to the selected user group. To make tasks from the supported task providers available in the SAP Task Center Web app, create a destination to every task provider you want to use. For more information, see [Destinations](../40-administration/destinations-3470733.md).

The end users can access the available on-screen help by choosing the SAP Companion icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the upper right corner of the Web app.

