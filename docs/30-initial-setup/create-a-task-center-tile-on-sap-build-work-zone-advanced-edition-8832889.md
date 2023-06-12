<!-- loio8832889d6e6f4620b4668154a574ba9a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Tile on SAP Build Work Zone, Advanced Edition

In the SAP BTP, Cloud Foundry environment you can create a *SAP Task Center* tile in the SAP Build Work Zone, advanced edition.



<a name="loio8832889d6e6f4620b4668154a574ba9a__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

-   You have a subscription to SAP Build Work Zone, advanced edition in your subaccount, and you have the `Workzone_Admin` role collection assigned to your user. For more information, see [What Is SAP Build Work Zone, Advanced Edition](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/5c0103b130de411fb2a4b5416e36d767.html).




<a name="loio8832889d6e6f4620b4668154a574ba9a__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center tile in SAP Build Work Zone, advanced edition. The Web app displays all tasks coming from the online connectors that are relevant for the logged-in user, harmonized by SAP Task Center. For more information about the Web app, see [Using SAP Task Center](../70-using-the-web-app/using-sap-task-center-7de5ff4.md).



<a name="loio8832889d6e6f4620b4668154a574ba9a__steps_z1d_mf2_vvb"/>

## Procedure

1.  Create a destination for the SAP Build Work Zone, advanced edition integration.

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

        ***Task\_Center***


        
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

2.  Create a Task Center tile in SAP Build Work Zone, advanced edition.

    1.  Build your own *Site Directory* link, as described in *Accessing the Site Manager* in [Site Manager in a Nutshell](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition-administrator/site-manager-in-nutshell) and open the link.
    2.  In the new window, go to *Channel Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *HTML 5 Apps* and choose *Update content*\( <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) below *Actions* to fetch the updated content.
    3.  Go to *Content Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *Content Explorer* tab, choose *HTML5 Apps*, select the *Task Center* item and choose *\+ Add to My Content*.
    4.  Go to the *My Content* tab where the *Task Center* app is added.
    5.  Choose *\+ New* \> *Group*.
    6.  Add a group title, assign the *Task Center* app from the *Assignments* section, and save your changes.
    7.  Assign the *Task Center* to a role in the *Content Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *My Content* tab.

        Choose one of the following options, depending on your visibility requirements:

        -   Assign *Task Center* to the existing *Everyone* role.

        -   Create a new role and assign the *Task Center* to it.


        For more information, see [Assign Apps to Roles](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/d0842269a2bd4b97a47ac19082e286a5.html).

    8.  Go to the *Site Directory* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). You can use an already existing site or create a new one \(*\+ Create Site*\).
    9.  From the *Site Editor* open the site \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). The Task Center tile is available now.
    10. Activate the languages from the site settings to enable the available translations for the Web app. For more information about the supported languages and how to activate them, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).
    11. \(Optional\) Activate the SAP Companion to enable on-screen help in the SAP Task Center Web app. For more information about the SAP Companion, see [SAP Enable Now](https://help.sap.com/viewer/product/SAP_ENABLE_NOW/latest/en-US?task=use_task).

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
        > Note, that you can't run both the SAP Companion for SAP Task Center and SAP Companion for SAP Build Work Zone, advanced edition in parallel. You can set up only one of them.





<a name="loio8832889d6e6f4620b4668154a574ba9a__result_h3j_4ss_tnb"/>

## Results

The integration of the SAP Task Center Web app in the SAP Build Work Zone, advanced edition is done and the Task Center tile is available. To get task from your task providers, you have to manually create a destination for every task provider you want to use. For more information, see [Destinations](../40-administration/destinations-3470733.md).

The end users can access the available on-screen help by choosing the SAP Companion icon \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) in the upper right corner of the Web app.

