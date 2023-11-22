<!-- loio1f8938105f22423188d67893eb08c67c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Tile on SAP Build Work Zone, standard edition

In the SAP BTP, Cloud Foundry environment you can create a Task Center tile in the SAP Build Work Zone, standard edition\(formerly known as SAP Build Work Zone\).



<a name="loio1f8938105f22423188d67893eb08c67c__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

-   You have a subscription to SAP Build Work Zone, standard edition in your subaccount, and you have the `Launchpad_Admin` role collection assigned to your user. For more information, see [Initial Setup](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/fd79b232967545569d1ae4d8f691016b.html).




<a name="loio1f8938105f22423188d67893eb08c67c__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center tile in the SAP Build Work Zone, standard edition. The Web app displays all tasks coming from the online connectors that are relevant for the logged-in user, harmonized by SAP Task Center. For more information about the Web app, see [Using SAP Task Center](../70-using-the-web-app/using-sap-task-center-7de5ff4.md).

> ### Note:  
> If you are already using SAP Cloud Portal service, you can continue with step 2 and replace *SAP Build Work Zone, standard edition* by *Cloud Portal Service*. For more information about the SAP Cloud Portal service, see [SAP Cloud Portal Service](https://help.sap.com/viewer/product/Portal_Service/1.0/en-US).



## Procedure

1.  Create a subscription to the SAP Build Work Zone, standard edition application.

    1.  Navigate to your subaccount in the SAP BTP cockpit.
    2.  In the navigation area under *Services*, choose *Service Marketplace*.
    3.  Choose the *SAP Build Work Zone, standard edition* tile.
    4.  Choose *Create*.
    5.  In the wizard, make sure that the service is set to *SAP Build Work Zone, standard edition*, the plan is set to *standard*, then choose *Create*.

2.  Create a destination for the SAP Build Work Zone, standard edition integration.

    If you have followed the [Automatic Setup](automatic-setup-3a49967.md), this destination is already created. You can continue with the next step.

    1.  In the navigation menu of your subaccount in the SAP BTP cockpit, choose *Destinations* \> *New Destination*.
    2.  In the *Destination Configuration* section, choose *Service Instance* and fill in the following information:


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
        
        Choose the SAP Task Center service instance you created in the *Prerequisites* section.
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Name*
        
        </td>
        <td valign="top">
        
        Add a name of the destination.
        
        </td>
        <td valign="top">
        
        **Example**:

        `Task_Center`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Description*
        
        </td>
        <td valign="top">
        
        \(Optional\) Add a description as a free text.
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        </table>
        
    3.  Choose *Next*.

        The additional properties are filled in automatically.

    4.  Save your destination.

3.  Create a Task Center tile in the SAP Build Work Zone, standard edition.

    1.  In the navigation menu of the SAP BTP cockpit in your subaccount, choose *Instances and Subscriptions*.
    2.  In the *Subscriptions* section, search for the *SAP Build Work Zone, standard edition* and choose *Go to Application* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\).
    3.  In the new window, open *Channel Manager*\(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\), search for *HTML 5 Apps*, and choose *Update content*\( <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) below *Actions* to fetch the updated content.
    4.  Go to *Content Manager*\(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\), and choose *Content Explorer*. Choose *HTML5 Apps*, select the *Task Center* item and choose *\+ Add*.
    5.  Go back to *Content Manager*, where the *Task Center* app is added.
    6.  Choose *Create* \> *Group*.
    7.  Add a group title, enable *Task Center* from the *Assignment Status* column, and save your changes.
    8.  Assign *Task Center* to a role in the *Content Manager*\(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)*.

        Choose one of the following options, depending on your visibility requirements:

        -   Assign *Task Center* to the existing *Everyone* role.

        -   Create a new role and assign *Task Center* to it.


        For more information, see [Assign Content to a Role](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/baeaf6ee364e48ac95dc09470281f174.html).

    9.  Go to the *Site Directory* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). You can assign *Task Center* to an already existing site, or create a new one \(*\+ Create Site*\). For more information, see [Create a Site](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/5778444e0419462bb4060a66a5c20de0.html).
    10. From the *Site Editor* open the site from the *Go to site* button \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). The Task Center tile is available now.
    11. Activate the languages from the site settings to enable the available translations for the Web app. For more information about the supported languages and how to activate them, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).
    12. \(Optional\) Activate the SAP Companion to enable on-screen help in the SAP Task Center Web app. For more information about the SAP Companion, see [SAP Enable Now](https://help.sap.com/viewer/product/SAP_ENABLE_NOW/latest/en-US?task=use_task).

        Follow the steps:

        1.  From the *Site Directory*\(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) open the *Site Settings*\(<span style="color:#346187;"><span class="SAP-icons"></span></span>\).
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
            
        4.  Save your site settings.

        > ### Restriction:  
        > Note, that you can't run both the SAP Companion for SAP Task Center and SAP Companion for SAP Build Work Zone, standard edition in parallel. You can set up only one of them. For more information, see [Restrictions - General](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/8cf196a5a8544c309086619df29595b1.html).





<a name="loio1f8938105f22423188d67893eb08c67c__result_h3j_4ss_tnb"/>

## Results

The integration of the SAP Task Center Web app in the SAP Build Work Zone, standard edition is done and the Task Center tile is available. To get task from your task providers, you have to manually create a destination for every task provider you want to use. For more information, see [Destinations](../40-administration/destinations-3470733.md).

The end users can access the available on-screen help by choosing the SAP Companion icon \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) in the upper right corner of the Web app.

