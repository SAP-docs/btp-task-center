<!-- loio1d3e69d3bcd044b892e7c6e145de19e5 -->

# Work with SAP Build Process Automation Tasks from a Different Subaccount

Follow the described procedure to complete the setup and receive tasks from SAP Build Process Automation instance, which is in a different subaccount than the SAP Task Center subaccount.



<a name="loio1d3e69d3bcd044b892e7c6e145de19e5__prereq_mrn_nvp_qjb"/>

## Prerequisites

-   You have a subaccount with an SAP Task Center service instance in the Cloud Foundry environment. In the following procedure we refer to this account as the 'SAP Task Center subaccount'.

-   You have created a second subaccount with an SAP Build Process Automation instance. In the following procedure we refer to this account as the 'SAP Build Process Automation subaccount'. This subaccount is configured to authenticate users via the same Identity Authentication server as the SAP Task Center subaccount.

-   You have performed the steps in [Set Up Principal Propagation Between Subaccounts](https://help.sap.com/docs/build-process-automation/sap-build-process-automation/set-up-principal-propagation-between-subaccounts-87df988656ad4190900c209b1d1780b0).


> ### Note:  
> Do not configure more than one destination to the same SAP Build Process Automation system for one SAP Task Center. This will result in having duplicate tasks for end users.



## Context

To work with tasks coming from an SAP Build Process Automation subaccount, you need to establish trust between the SAP Build Process Automation subaccount and the SAP Task Center subaccount.



## Procedure

1.  Download the metadata XML file of your Cloud Foundry subaccount in which SAP Build Process Automation is running. To download the file, navigate to the subaccount in your cockpit, go to *Security* \> *Trust Configuration* and choose *SAML Metadata*.

    From the XML you need the following parameters to complete the destination setup:

    -   `entityID`

    -   The `Location` value from the `AssertionConsumerService` element, where `Binding="urn:oasis:names:tc:SAML:2.0:bindings:URI"` 


2.  Navigate to your SAP Task Center subaccount and select the *Connectivity* \> *Destinations* tab from the navigation area on the left.

3.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *SAPBuildPA\_rem* \(for working from a different subaccount\). You can use the sample destination or clone it, and update the properties as described in the table below.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described below.

4.  Configure the properties of the destination as described in the following table:


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

    `SAPBuildPA_rem`
    
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
    
    Add the *endpoints \> api* value from the *Prerequisites* in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md) and append */internal/workflow/rest/v1* to the URL.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://spa-api-gateway-sample.cfapps.sap.hana.ondemand.com/internal/workflow/rest/v1`
    
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
    
    Add the *entityID* value from Step 1.
    
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
    
    Add the *clientid* value from the *Prerequisites* in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
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
    
    Add the *Location* value from Step 1.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://subaccount.authentication.eu10.hana.ondemand.com/oauth/token/alias/subaccount.aws-live-eu10`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the *clientid* value from the *Prerequisites* in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `sb-clone-b0610b21-dbf4-49bf-a6d2-5efef90e2736!b5550|xsuaa!b2746`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the *clientsecret* value from the *Prerequisites* in [Connect SAP Build Process Automation and SAP Task Center](connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md).
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
5.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
    *tc.notifications.enabled*
    
    </td>
    <td valign="top">
    
    \(Optional\) Enable this property to turn on SAP Task Center notifications for end users.

    Accepted values are `true` and `false`.

    The default value is `false`. If no value is provided, the property is set to `false`.

    > ### Note:  
    > Any value other than `true` and `false` sets the connector in status *Warning*.

    This property, combined with the *Alert\_Notification\_Connectivity\_ANS* destination, allows you to decide if end users should receive notifications from SAP Build Process Automation, or both SAP Task Center and SAP Build Process Automation.

    -   If the property is set to `true` and you have set up the *Alert\_Notification\_Connectivity\_ANS* destination as described in [Enable Notifications](https://help.sap.com/docs/build-process-automation/sap-build-process-automation/enable-notifications), then the end users will receive notifications from both SAP Task Center and SAP Build Process Automation. This might include duplicate notifications for created or forwarded tasks.
    -   \(Recommended\) If the property is set to `false` and you have set up *Alert\_Notification\_Connectivity\_ANS* as described in [Enable Notifications](https://help.sap.com/docs/build-process-automation/sap-build-process-automation/enable-notifications), then the end users will receive notifications only from SAP Build Process Automation and not from SAP Task Center.


    
    </td>
    <td valign="top">
    
    **Example**:

    `false`
    
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

    `SPA`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.task.ui.url*
    
    </td>
    <td valign="top">
    
    Add this property to access the SAP Build Process Automation tasks without the need of an additional central point of entry for accessing application for SAP Build Process Automation.

    The value of this property must follow the pattern: `https://<root_url>/comsapspaprocessautomation.comsapspainbox/taskui.html`

    To get the correct URL, open My Inbox in the SAP Build Process Automation Lobby, copy the URL of My Inbox and replace `inbox.html` page with `taskui.html`.

    For more information on how to access My Inbox in the SAP Build Process Automation Lobby, see [Use My Inbox](https://help.sap.com/docs/build-process-automation/sap-build-process-automation/using-my-inbox).

    > ### Note:  
    > -   Custom themes are not supported for task UI visualization.
    > 
    > -   This property is not mandatory if you use SAP Build Process Automation on SAP Build Work Zone, standard edition.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://<root_url>/comsapspaprocessautomation.comsapspainbox/taskui.html`
    
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

    `SAP Build Process Automation`
    
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

    `SAP Build Process Automation Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Build Process Automation Aufgabe`
    
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
    
6.  Choose *Save*.

7.  \(Optional\) To check the connectivity between the SAP Task Center service and the SAP Build Process Automation, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive the correct information about the connectivity between the SAP Task Center service and the SAP Build Process Automation.


