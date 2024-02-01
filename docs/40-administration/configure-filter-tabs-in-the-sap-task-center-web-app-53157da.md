<!-- loio53157da9e7ed498ea6b30298bf7d5213 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Filter Tabs in the SAP Task Center Web App

You can configure filter tabs for the semantic grouping of tasks in the SAP Task Center Web app.

The destination in the SAP BTP cockpit, configured for connectivity from SAP Task Center to the target task-provider systems, is configured with the following additional properties, which enable the semantic grouping feature in the SAP Task Center Web app:

-   *tc.provider\_type*

-   *tc.ui.group*


For more information about the target task-provider systems and their setup, see [Destinations](destinations-3470733.md).

The SAP Task Center Web app provides the following filter tabs by default:

-   *All* - always available on first position; contains all tasks
-   *Failed Tasks* - appears only if there are tasks, which failed during processing
-   *Others* - always on last position; appears only if there is at least one custom filter tab

Administrators can create custom filter tabs, based on the following semantics:

-   Destinations are grouped based on the *tc.ui.group* property.

    The value of this property is displayed as the name of the filter tab.

    If you want to use translations for the filter tab names, you have to add the default *tc.ui.group* property, and also add the *tc.ui.group.\[language\_code\]* for the respective language \(for example, *tc.ui.group.de-DE* for German translations\) with the translation as value of the property.

    For more information about the supported languages and language codes, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

    Depending on the browser language of the user, SAP Task Center searches for available translations as follows:

    1.  If there is a *tc.ui.group.\[language\_code\]* property defined for the browser language of the user, then the value of this property is visualized as translation of the filter tab name.

    2.  If there is no *tc.ui.group.\[language\_code\]* property defined for the browser language of the user, but the default *tc.ui.group* property is defined, then the value of the default *tc.ui.group* property is visualized as translation of the filter tab name.

    3.  If there are no *tc.ui.group* and *tc.ui.group.\[language\_code\]* properties defined, the tasks will be found in the *Others* filter tab.


    > ### Restriction:  
    > Please note that the values *All* and *Failed Tasks* are reserved by the SAP Task Center Web app and should not be used as values of the *tc.ui.group* property.
    > 
    > Though if you use *All* or *Failed Tasks* as value to the *tc.ui.group* property of a destination, the tasks retrieved from these destinations will be shown in the standard *All* or *Failed Tasks* filter tabs.

-   If the values of *tc.ui.group* of two or more destinations are the same, but the values of *tc.provider\_type* of the same destinations are different, then the Web app groups those destinations into one filter tab, and displays a generic icon.

-   A predefined icon, based on the *tc.provider\_type* property value, is displayed for each filter tab. Here is the list of predefined icons:


    <table>
    <tr>
    <th valign="top">

    Task Provider
    
    </th>
    <th valign="top">

    Value of *tc.provider\_type*
    
    </th>
    <th valign="top">

    Icon
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Advanced Financial Closing
    
    </td>
    <td valign="top">
    
    `AFC`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Ariba
    
    </td>
    <td valign="top">
    
    `Ariba`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Process Automation
    
    </td>
    <td valign="top">
    
    `SPA`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, advanced edition
    
    </td>
    <td valign="top">
    
    `WorkZone`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Cloud for Customer
    
    </td>
    <td valign="top">
    
    `C4C`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Concur
    
    </td>
    <td valign="top">
    
    `Concur`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Fieldglass
    
    </td>
    <td valign="top">
    
    `Fieldglass`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Marketing Cloud
    
    </td>
    <td valign="top">
    
    `SMC`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP S/4HANA
    
    </td>
    <td valign="top">
    
    `S/4HANA`
    
    </td>
    <td valign="top" rowspan="3">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP S/4HANA Cloud, public edition
    
    </td>
    <td valign="top">
    
    `S/4HANACloud`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP S/4HANA Cloud, private edition
    
    </td>
    <td valign="top">
    
    `S/4HANAPrivateCloud`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP SuccessFactors
    
    </td>
    <td valign="top">
    
    `SuccessFactors`
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>
    
    </td>
    </tr>
    </table>
    
-   The tasks provided by destinations, for which the *tc.ui.group* property is not maintained, are grouped into the *Others* filter tab \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) in the SAP Task Center Web app.

    > ### Note:  
    > The *Others* filter tab is only displayed if there is at least one more filter tab, in addition to the *All* filter tab.


