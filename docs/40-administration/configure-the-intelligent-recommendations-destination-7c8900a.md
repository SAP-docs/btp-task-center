<!-- loio7c8900a80b444691a4c46d9369dfc466 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure the Intelligent Recommendations Destination

Set up an additional destination for the *Intelligent Recommendations* feature.



<a name="loio7c8900a80b444691a4c46d9369dfc466__section_nvq_spk_lcc"/>

## Prerequisites

-   You must have set up a primary destination for the connection to SAP Build Process Automation. For more information, see [Work with SAP Build Process Automation Tasks from the Same Subaccount](work-with-sap-build-process-automation-tasks-from-the-same-subaccount-f9c57ee.md) or [Work with SAP Build Process Automation Tasks from a Different Subaccount](work-with-sap-build-process-automation-tasks-from-a-different-subaccount-1d3e69d.md).

    > ### Note:  
    > The *Intelligent Recommendations* feature is currently available only for SAP Build Process Automation tasks and only on the data centers described in the SAP Note [3514669](https://me.sap.com/notes/3514669).

-   You have set up the SAP Task Center Administration application and you have the `TaskCenterBusinessAdministrator` role assigned. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).

-   You have set up the *Task\_Center* destination from your SAP Task Center service instance. For more information, see [Destination for the Central Point of Entry for Accessing Applications](destination-for-the-central-point-of-entry-for-accessing-applications-10320af.md).

    Make sure that you update the *HTML 5 Apps* content in your central point of entry for accessing applications.

    > ### Caution:  
    > If you have set up the *Task\_Center* destination to the central point of entry for accessing applications before the release of the *Intelligent Recommendations* feature in September 2024, you must delete the existing *Task\_Center* destination and create a new one manually, following the [Destination for the Central Point of Entry for Accessing Applications](destination-for-the-central-point-of-entry-for-accessing-applications-10320af.md) documentation. After that, make sure that you update the *HTML 5 Apps* content on the *Channel Manager*\(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\) tab in your central point of entry for accessing applications. See [Create a Task Center Tile](../30-initial-setup/create-a-task-center-tile-70e7f6e.md).

-   Make sure you are aware of the *Customer Data Usage for Continuous Improvement of the AI Model* described in [Data Protection and Privacy](../60-security/data-protection-and-privacy-8bd310a.md).




<a name="loio7c8900a80b444691a4c46d9369dfc466__section_iqf_5pk_lcc"/>

## Concept

This destination is required for the usage of the *Intelligent Recommendations* feature, available in the SAP Task Center Administration app.

The *Intelligent Recommendations* feature offers a new filter option *Confidence Level* to the end users in the SAP Task Center Web app. The *Confidence Level* filter provides end users with information about the approval confidence of the tasks, which is calculated by a trained AI model. See also [Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md).



<a name="loio7c8900a80b444691a4c46d9369dfc466__section_cvl_vpk_lcc"/>

## Procedure

Choose one of the two options to create a destination for the *Intelligent Recommendations* feature, depending on the location of your SAP Build Process Automation and SAP Task Center subaccounts:



### SAP Build Process Automation and SAP Task Center Are in the Same Subaccount

If SAP Build Process Automation and SAP Task Center are in the same subaccount, follow the procedure:

1.  In the navigation menu of your subaccount in the SAP BTP cockpit, choose *Connectivity* \> *Destinations* \> *Create Destination* \> *Blank Template* and fill in the following properties in the *Destination Configuration* section:


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
    
    *Name*
    
    </td>
    <td valign="top">
    
    Add a name of the destination, following the pattern `<name of primary destination>_AI`.

    The destination name for the *Intelligent Recommendations* feature must be the same as the name of the primary destination, with the suffix `_AI`.

    > ### Example:  
    > For example, if the name of the primary destination is `SAPBuildPA`, the name of the intelligent recommendations destination should be `SAPBuildPA_AI`.

    For more information on the primary destination, see [Work with SAP Build Process Automation Tasks from the Same Subaccount](work-with-sap-build-process-automation-tasks-from-the-same-subaccount-f9c57ee.md) or [Work with SAP Build Process Automation Tasks from a Different Subaccount](work-with-sap-build-process-automation-tasks-from-a-different-subaccount-1d3e69d.md).

    > ### Note:  
    > Please note that if you don't follow the described pattern, you will not be able to set up an Intelligent Recommendations model.

    If you change the name of an already configured destination, the administrators will not be able to see the created AI models in the SAP Task Center Administration app.
    
    </td>
    <td valign="top">
    
    **Example**:

    `SAPBuildPA_AI`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Choose the *HTTP* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
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
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    Add the *endpoints \> api* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://spa-api-gateway-eu10.cfapps.sap.hana.ondemand.com`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy type*
    
    </td>
    <td valign="top">
    
    Choose the *Internet* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    Choose the *OAuth2ClientCredentials* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client ID*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> clientid* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `sb-clone-abcd1234-ab12-ab12-ab12-abcdef123456!ab123|xsuaa!abc12`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> clientsecret* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> url* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://subaccount.authentication.eu10.hana.ondemand.com`
    
    </td>
    </tr>
    </table>
    
2.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
    *HTML5.DynamicDestination*
    
    </td>
    <td valign="top">
    
    Set this property to `true`.

    This property indicates that the destination can be dynamically resolved at runtime, typically for use with HTML5 applications that are deployed as part of the SAP BTP, Cloud Foundry environment.
    
    </td>
    <td valign="top">
    
    **Value**:

    `true`
    
    </td>
    </tr>
    </table>
    
3.  Save your destination.




### SAP Build Process Automation and SAP Task Center Are in Different Subaccounts

If SAP Build Process Automation and SAP Task Center are in the different subaccounts, follow the procedure:

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, choose *Connectivity* \> *Destinations* \> *Create Destination* \> *Blank Template* and fill in the following properties in the *Destination Configuration* section.


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
    
    *Name*
    
    </td>
    <td valign="top">
    
    Add a name of the destination, following the pattern `<name of primary destination>_AI`.

    The destination name for the *Intelligent Recommendations* feature must be the same as the name of the primary destination, with the suffix `_AI`.

    > ### Example:  
    > For example, if the name of the primary destination is `SAPBuildPA`, the name of the intelligent recommendations destination should be `SAPBuildPA_AI`.

    For more information on the primary destination, see [Work with SAP Build Process Automation Tasks from the Same Subaccount](work-with-sap-build-process-automation-tasks-from-the-same-subaccount-f9c57ee.md) or [Work with SAP Build Process Automation Tasks from a Different Subaccount](work-with-sap-build-process-automation-tasks-from-a-different-subaccount-1d3e69d.md).

    > ### Note:  
    > Please note that if you don't follow the described pattern, you will not be able to set up an Intelligent Recommendations model.


    
    </td>
    <td valign="top">
    
    **Example**:

    `SAPBuildPA_AI`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Choose the *HTTP* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
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
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    Add the *endpoints \> api* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://spa-api-gateway-eu10.cfapps.sap.hana.ondemand.com`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy type*
    
    </td>
    <td valign="top">
    
    Choose the *Internet* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    Choose the *OAuth2ClientCredentials* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client ID*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> clientid* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `sb-clone-abcd1234-ab12-ab12-ab12-abcdef123456!ab123|xsuaa!abc12`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> clientsecret* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> url* value from the *Prerequisites* section in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://subaccount.authentication.eu10.hana.ondemand.com`
    
    </td>
    </tr>
    </table>
    
2.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
    *HTML5.DynamicDestination*
    
    </td>
    <td valign="top">
    
    Set this property to `true`.

    This property indicates that the destination can be dynamically resolved at runtime, typically for use with HTML5 applications that are deployed as part of the SAP BTP, Cloud Foundry environment.
    
    </td>
    <td valign="top">
    
    **Value**:

    `true`
    
    </td>
    </tr>
    </table>
    
3.  Save your destination.




<a name="loio7c8900a80b444691a4c46d9369dfc466__section_adn_5zz_lcc"/>

## Next Steps

Once having set up the new destination for intelligent recommendations, you can continue with setting up intelligent recommendation models. For more information, see [Working with Intelligent Recommendations](working-with-intelligent-recommendations-340651c.md).

