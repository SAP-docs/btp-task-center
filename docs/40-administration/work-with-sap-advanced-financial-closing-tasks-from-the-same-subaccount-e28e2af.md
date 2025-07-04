<!-- loioe28e2af5932d4d33aa4063a94885f5ac -->

# Work with SAP Advanced Financial Closing Tasks from the Same Subaccount

Follow the procedure below to complete the setup and receive tasks from an SAP Advanced Financial Closing instance in the same subaccount as the SAP Task Center instance.



<a name="loioe28e2af5932d4d33aa4063a94885f5ac__prereq_xhk_hw3_rzb"/>

## Prerequisites

-   Make sure you have the parameters enlisted in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md).

-   You have completed the setup in [How to Set Up the SAP Task Center Integration Using the Same Subaccount](https://help.sap.com/docs/advanced-financial-closing/administration/how-to-set-up-sap-task-center-integration-using-same-subaccount).




## Context

> ### Note:  
> Do not configure more than one destination to the same SAP Advanced Financial Closing system for one SAP Task Center. This will result in having duplicate tasks for end users.



<a name="loioe28e2af5932d4d33aa4063a94885f5ac__steps_tq2_qs2_tpb"/>

## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> *Destinations* tab from the navigation area on the left.

2.  Create a new destination and manually add the properties as described below.

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
    
    The destination name can be up to 64 characters.

    > ### Note:  
    > The name of the destination must not be longer than 64 characters, as otherwise, the status of the respective SAP Task Center connector will be set to `Error`.

    > ### Note:  
    > If you change the *name* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `AFC`
    
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
    
    Add the *endpoints \> task-center* value from the *Prerequisites* in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md) and remove `/task-provider/v2` from the URL.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://afc-production-afc-api.cfapps.eu10.hana.ondemand.com/api`
    
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
    
    Add the *uaa \> url* value from the *Prerequisites* in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://subaccount.authentication.eu10.hana.ondemand.com`
    
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
    
    Add the *uaa \> clientid* value from the *Prerequisites* in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `sb-clone-b0610b21-dbf4-49bf-a6d2-5efef90e2736!b5550|xsuaa!b2746`
    
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
    
    Add the *uaa \> url* value from the *Prerequisites* in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md) and append `/oauth/token` to the URL.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://subaccount.authentication.eu10.hana.ondemand.com/oauth/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> clientid* value from the *Prerequisites* in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `sb-92c762c9-9dd3-40b9-a2db-78607318901b!b16506|afc-api-dev!b5874`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the *uaa \> clientsecret* value from the *Prerequisites* in [Connect SAP Advanced Financial Closing and SAP Task Center](connect-sap-advanced-financial-closing-and-sap-task-center-2873c51.md).
    
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
    
    \(Optional\) Enable this property to turn on the notifications for end users.

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
    
    *tc.inbox.pull.days*
    
    </td>
    <td valign="top">
    
    \(Optional\) By default, the initial pull job of SAP Task Center loads tasks that have been updated or created in the past 90 days. You can adjust this period to a maximum of 180 days by configuring the *tc.inbox.pull.days* property. The allowed values range from 0 to 180.

    Please note that this property is available only with the `all-tasks` service plan. For more information on the service plan and its details, see [Service Plans and Metering](../10-what-is/service-plans-and-metering-7b6b689.md).

    After setting this property, you must trigger the initial pull job for this task provider by repopulating the task cache, as described in [Repopulate the Task Cache](repopulate-the-task-cache-e93aa71.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `180`
    
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

    `AFC`
    
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

    `SAP Advanced Financial Closing`
    
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

    `SAP Advanced Financial Closing Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Advanced Financial Closing Aufgabe`
    
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

6.  \(Optional\) To check the connectivity between the SAP Task Center service and the SAP Advanced Financial Closing, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive the correct information about the connectivity between the SAP Task Center service and the SAP Advanced Financial Closing.


