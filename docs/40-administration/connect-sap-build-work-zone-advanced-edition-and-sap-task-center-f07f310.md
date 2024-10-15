<!-- loiof07f3103d40447d6bfbb0ae0b7920f6a -->

# Connect SAP Build Work Zone, advanced edition and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from SAP Build Work Zone, advanced edition instance in the same \(local\) subaccount as the SAP Task Center instance on SAP BTP, Cloud Foundry environment.



## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP BTP Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-btp-integration-scenario).

-   You must have performed the steps in [Integration with SAP Task Center](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/integration-with-sap-task-center). You need the following parameters for the setup of this destinations:

    -   *API Endpoint*
    -   *Audience*
    -   *Client Key*
    -   *Token Service URL*
    -   *Token Service User*
    -   *Token Service Password*




<a name="loiof07f3103d40447d6bfbb0ae0b7920f6a__context_b2g_cr4_hyb"/>

## Context

> ### Note:  
> Do not configure more than one destination to the same SAP Build Work Zone, advanced edition system for one SAP Task Center. This will result in having duplicate tasks for end users.



<a name="loiof07f3103d40447d6bfbb0ae0b7920f6a__steps_tq2_qs2_tpb"/>

## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> *Destinations* tab from the navigation area.

2.  If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described in the table.

3.  Configure the properties of the destination as described in the following table:


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
    
    The destination name can be up to 16 characters.

    > ### Note:  
    > The name of the destination must not be longer than 16 characters, as otherwise, the status of the respective SAP Task Center connector will be set to `Error`.

    > ### Note:  
    > If you change the *name* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `WorkZone`
    
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
    
    Add the *API endpoint* value from the *Prerequisites* section.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://sample.workzone.ondemand.com/api/v2`
    
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
    
    Choose the *OAuth2SAMLBearerAssertion* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Audience*
    
    </td>
    <td valign="top">
    
    Add the *Audience* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://sample.workzone.ondemand.com/`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *AuthnContextClassRef*
    
    </td>
    <td valign="top">
    
    Defines which mechanism is used to authenticate the user through *AuthnContextClassRef*.
    
    </td>
    <td valign="top">
    
    **Value**:

    `urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Key*
    
    </td>
    <td valign="top">
    
    Add the *Client Key* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `AWtZNx9LX8vxeQ4Ui9DS`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL Type*
    
    </td>
    <td valign="top">
    
    Choose *Dedicated*.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    Add the *Token Service URL* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://sample.workzone.ondemand.com/api/v2/auth/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the *Token Service User* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `AWtZNx9LX8vxeQ4Ui9DS`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the *Token Service Password* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
4.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
    *nameIdFormat*
    
    </td>
    <td valign="top">
    
    Indicates the SAML name identifier formats supported by the Single Sign-On service.
    
    </td>
    <td valign="top">
    
    **Value**:

    `urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.enabled*
    
    </td>
    <td valign="top">
    
    Enables SAP Task Center to connect to the configured task provider destination.

    > ### Caution:  
    > If you are using the sample destinations created by the booster \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you must add the *tc.enabled* property manually. Without this property, the destination cannot be used by SAP Task Center.

    > ### Note:  
    > Any value other than `true` \(for example `false`\) would have the following effects:
    > 
    > -   The previously stored tasks are kept in the task cache.
    > 
    > -   The tasks from this destination are **not** displayed in the SAP Task Center Web app.
    > 
    > -   The task cache is not updated with tasks from this destination.
    > 
    > 
    > If you want to delete the task cache and repopulate it for this destination, see [Repopulate the Task Cache](repopulate-the-task-cache-e93aa71.md).


    
    </td>
    <td valign="top">
    
    **Value**:

    `true`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.notifications.enabled*
    
    </td>
    <td valign="top">
    
    \(Optional\) Enable this property to turn on the notifications for end users, sent by SAP Alert Notification service for SAP BTP.

    Accepted values are `true` and `false`.

    The default value is `false`. If no value is provided, the property is set to `false`.

    > ### Note:  
    > Any value other than `true` and `false` sets the connector in status *Warning*.


    
    </td>
    <td valign="top">
    
    **Example**:

    `true`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.provider\_type*
    
    </td>
    <td valign="top">
    
    Type of the task provider. This property is needed if you want to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md). 
    
    </td>
    <td valign="top">
    
    **Value**:

    `WorkZone`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.ui.group*

    and

    *tc.ui.group.\[language\_code\]*
    
    </td>
    <td valign="top">
    
    \(Optional\) Provides grouping for the SAP Task Center Web app *Filter Tabs*.

    You can define a separate property for a filter tab translation for each of the supported languages \(see [Supported Languages](../10-what-is/supported-languages-c66c693.md)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.group* property with the value `<default_translation>` for a default translation of the group name.

    -   the *tc.ui.group.de-DE* property with the value `<German_translation>` for a German translation of the group name.


    For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `SAP Build Work Zone, advanced edition`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.ui.label* 

    and

    *tc.ui.label.\[language\_code\]*
    
    </td>
    <td valign="top">
    
    \(Optional\) Provides additional information about the task. The value of the property is displayed in the *Task* column of the SAP Task Center Web app under the *Task Title*.

    You can define a separate property for a task label translation for each of the supported languages \(see [Supported Languages](../10-what-is/supported-languages-c66c693.md)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.label* property with the value `<default_translation>` for a default translation of the label.

    -   the *tc.ui.label.de-DE* property with the value `<German_translation>` for a German translation of the label.


    For more information, see [Configure Labels in SAP Task Center Web App](configure-labels-in-sap-task-center-web-app-a0be9ad.md).
    
    </td>
    <td valign="top">
    
    **Example for *tc.ui.label***:

    `SAP Build Work Zone, advanced edition Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Build Work Zone, advanced edition Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tokenServiceURL.headers.authAttribute*
    
    </td>
    <td valign="top">
    
    The value of this property is needed during token retrieval.
    
    </td>
    <td valign="top">
    
    **Value**:

    `user_uuid`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *userIdSource*
    
    </td>
    <td valign="top">
    
    Provides information about the `userIdSource`to SAP Cloud Identity Services - Identity Authentication.
    
    </td>
    <td valign="top">
    
    **Value**:

    `user_uuid`
    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*.

6.  \(Optional\) To check the connectivity between the SAP Task Center service and the SAP Build Work Zone, advanced edition, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive the correct information about the connectivity between the SAP Task Center service and the SAP Build Work Zone, advanced edition.


