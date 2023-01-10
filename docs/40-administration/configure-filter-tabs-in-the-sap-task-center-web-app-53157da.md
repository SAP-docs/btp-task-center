<!-- loio53157da9e7ed498ea6b30298bf7d5213 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Filter Tabs in the SAP Task Center Web App

You can configure filter tabs for the semantic grouping of tasks in the SAP Task Center Web app.

The destination in the SAP BTP cockpit, configured for connectivity from SAP Task Center to the target task-provider systems, is configured with the following additional properties, which enable the semantic grouping feature in the SAP Task Center Web app:

-   *tc.provider\_type*

-   *tc.ui.group*


For more information about the target task-provider systems and their setup, see [Destinations](destinations-3470733.md).

The SAP Task Center Web app generates *Filter Tabs* based on the following semantics:

-   Destinations are grouped based on the *tc.ui.group* property. The value of this property is displayed as the name of the filter tab.

    If you want to use translations for the filter tab names, you have to add the default *tc.ui.group* property and then also add the property for the respective language *tc.ui.group.\[language\_code\]*. For example, *tc.ui.group.de-DE* for German translations. For more information about the supported languages, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

    Depending on your user language, SAP Task Center searches for available translations as follows:

    -   If there is a *tc.ui.group.\[language\_code\]* property defined for the user language, then the filter tab translations for this language are visualized in the respective language.

    -   If the *tc.ui.group.\[language\_code\]* property for the user language is not defined, but the default *tc.ui.group* property is defined, then the filter tab translations are visualized in the default language.

    -   If there are no *tc.ui.group* and *tc.ui.group.\[language\_code\]* properties defined, the tasks are displayed in the *Others* filter tab.


    > ### Restriction:  
    > Please note that the *All* value of the *tc.ui.group* property is reserved by the SAP Task Center Web app. Therefore, the destinations, for which the *tc.ui.group* value is *All*, will not be grouped into a separate filter tab in the SAP Task Center Web app.
    > 
    > Instead, the tasks retrieved from these destinations will be shown in the standard *All* filter tab in the SAP Task Center Web app.

-   If the values of *tc.ui.group* match, but the values of *tc.provider\_type* do not match, then the SAP Task Center Web app groups those destinations into a filter tab and displays a generic icon.

-   A predefined icon based on *tc.provider\_type* property value is displayed for each filter tab. For more information see the table below:


    <table>
    <tr>
    <th valign="top">

    Destination Type


    
    </th>
    <th valign="top">

    Icon


    
    </th>
    </tr>
    <tr>
    <td valign="top">

    SAP Ariba


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    SAP Cloud for Customer


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    SAP Fieldglass


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    SAP Build Process Automation


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    SAP S/4HANA


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    SAP SuccessFactors


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Others


    
    </td>
    <td valign="top">

    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > If you select a *tc.provider\_type* different from the expected value for the destination type, the SAP Task Center Web app displays a Generic icon \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) for the configured filter tabs.

-   The tasks provided by destinations for which the *tc.ui.group* property is not maintained are grouped into the *Others* filter tab in the SAP Task Center Web app.

    > ### Note:  
    > The *Others* filter tab is only displayed if there is at least one additional filter tab.


