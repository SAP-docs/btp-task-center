<!-- loio9367f0d41a394cfca76ddda7a69639d5 -->

# Connect SAP Fieldglass and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP Fieldglass on SAP BTP, Cloud Foundry environment



<a name="loio9367f0d41a394cfca76ddda7a69639d5__prereq_zzy_spz_pjb"/>

## Prerequisites

> ### Tip:  
> ![](../30-initial-setup/images/28x28_launch_png_2484bce.png) See also the step-by-step mission for the setup of connection to SAP Fieldglass at [Integrate Your SAP Fieldglass Tasks Into SAP Task Center](https://discovery-center.cloud.sap/missiondetail/3911/4077/).

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP Fieldglass Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-fieldglass-integration-scenario).

-   You need to have an existing SAP Fieldglass tenant.

-   You have completed the steps described in [Enable SAP Task Center in SAP Fieldglass](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/3fabeb5092a44edd8fc3dd4b4cbc6b9e.html) to enable the functionality in SAP Fieldglass.


> ### Note:  
> Do not configure more than 1 destination to the same SAP Fieldglass system for 1 SAP Task Center. This will result in having duplicate tasks for end users.



## Procedure

1.  Create a new service instance to enable task updates to be pushed from SAP Fieldglass. Follow the steps in [Create a Service Instance Using the SAP BTP Cockpit](../30-initial-setup/create-a-service-instance-using-the-sap-btp-cockpit-dc9af9f.md) and create a service key for the service instance. Open the JSON file of the service key and get the following values:

    -   *endpoints* \> *inbox\_rest\_url*
    -   *uaa* \> *url*
    -   *uaa* \> *clientid*
    -   *uaa* \> *clientsecret*

2.  Follow the steps described in [Manage SAP Task Center to Enable Push of Task Updates](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/028e198df0284ff09662aa279a25b00f.html) to enable task updates to be pushed from SAP Fieldglass.

3.  Follow the steps described in [Create API Application Key](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/1a32d66883814f58b4dbfcf22d4b16ae.html). You need the following property values to complete the setup:

    -   *Client ID*
    -   *Client Secret*
    -   *Virtual Person Name \(Username\)*
    -   *License Key*
    -   *API Application Key*

    > ### Note:  
    > If the *API Application Key* has already been created for SAP Task Center, you need to have access to the *Web Services* section on the [View Application Key](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/d978fde7578444d9bd8b79e2af6c46d2.html) page in the SAP Fieldglass Configuration Manager to copy the properties.
    > 
    > If the *Web Services* section is blank, please contact [SAP Fieldglass Customer Support](https://www.fieldglass.com/customer-support) to get the values.

4.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> ***Destinations* tab from the navigation area.

5.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *Fieldglass*. You can use the sample destination or clone it, and update the properties as described in the following table.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described in the following table.

6.  Configure the properties of the destination as described next:


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
    > The name of the destination must not be longer than 64 characters, otherwise, the status of the respective SAP Task Center connector will be set to `Error`.

    > ### Note:  
    > If you change the *name* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `Fieldglass`
    
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
    
    Use the SAP Fieldglass tenant URL, used to log into the user interface, or the one provided by SAP Fieldglass support.

    For US datacenter, use [https://www.fieldglass.net/api/v1](https://www.fieldglass.net/api/v1).

    For EU datacenter, use[https://www.fieldglass.eu/api/v1](https://www.fieldglass.eu/api/v1).

    If you don’t know which SAP Fieldglass datacenter you are using, please contact SAP Fieldglass [Customer Support](https://www.fieldglass.com/customer-support).

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    If `https://ie1.fgvms.com` is the instance you are using to log in, then the URL should be `https://ie1.fgvms.com/api/v1`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
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
    
    The *Audience* is used to construct the SAML assertion.
    
    </td>
    <td valign="top">
    
    **Example**:

    `Fieldglass`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *AuthnContextClassRef*
    
    </td>
    <td valign="top">
    
    Value of the `AuthnContextClassRef` tag, which is part of the generated `OAuth2SAMLBearerAssertion` authentication.
    
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
    
    Add the `API Application Key` value located on the *View Application Keys* page in SAP Fieldglass Configuration Manager.
    
    </td>
    <td valign="top">
    
    **Value** of `API Application Key`
    
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
    
    Use the SAP Fieldglass tenant URL, used to log into the user interface, or the one provided by SAP Fieldglass support.

    For US datacenter, use [http://fieldglass.net/api/oauth2/v2.0/token](http://fieldglass.net/api/oauth2/v2.0/token).

    For EU datacenter, use [http://fieldglass.eu/api/oauth2/v2.0/token](http://fieldglass.eu/api/oauth2/v2.0/token).

    If you don’t know which SAP Fieldglass datacenter you are using, please contact the SAP Fieldglass [Customer Support](https://www.fieldglass.com/customer-support).
    
    </td>
    <td valign="top">
    
    **Example**:

    If `https://ie1.fgvms.com` is the instance you are using to log in, then the URL should be `https://ie1.fgvms.com/api/oauth2/v2.0/token`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the `Virtual Person Name (Username)` value located in the *Web Services* section on the *View Application Keys* page in SAP Fieldglass Configuration Manager.
    
    </td>
    <td valign="top">
    
    **Value** of `Virtual Person Name (Username)`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the `License Key` value located in the *Web Services* section on the *View Application Keys* page in SAP Fieldglass Configuration Manager.
    
    </td>
    <td valign="top">
    
    **Value** of `License Key`
    
    </td>
    </tr>
    </table>
    
7.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
    Value of the `NameIdFormat` tag, which is part of the generated `OAuth2SAMLBearerAssertion` authentication.
    
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
    > Any value other than `true` \(for example `false`\) would has the following effects:
    > 
    > -   The previously stored tasks are kept in the `Task Cache`.
    > 
    > -   The tasks from this destination are **not** available in the SAP Task Center Web app.
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
    
    *tc.clientId*
    
    </td>
    <td valign="top">
    
    This property is used to enable task updates to be pushed from SAP Fieldglass.

    The value of this property is the value of the *uaa* \> *clientid* from the service key of the new service instance \(see *Step 1*\).

    > ### Note:  
    > Set this property only when you have enabled task updates to be pushed from SAP Fieldglass \(see *Step 2*\). If you haven't completed this step, you might not be able to receive tasks from SAP Fieldglass.


    
    </td>
    <td valign="top">
    
    **Value** of *clientid*
    
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
    
    *tc.provider\_type*
    
    </td>
    <td valign="top">
    
    Type of the task provider. This property is needed if you want to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md). 
    
    </td>
    <td valign="top">
    
    **Value**:

    `Fieldglass`
    
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

    `SAP Fieldglass`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.ui.label* 

    and

    *tc.ui.label.\[language\_code\]*
    
    </td>
    <td valign="top">
    
    \(Optional\) Provides additional information about the task. The value of the property is available in the *Task* column of the SAP Task Center Web app under the *Task Title*.

    You can define a separate property for a task label translation for each of the supported languages \(see [Supported Languages](../10-what-is/supported-languages-c66c693.md)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.label* property with the value `<default_translation>` for a default translation of the label.

    -   the *tc.ui.label.de-DE* property with the value `<German_translation>` for a German translation of the label.


    For more information, see [Configure Labels in SAP Task Center Web App](configure-labels-in-sap-task-center-web-app-a0be9ad.md).
    
    </td>
    <td valign="top">
    
    **Example for *tc.ui.label***:

    `SAP Fieldglass Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Fieldglass Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tokenServiceURL.queries.client\_id*
    
    </td>
    <td valign="top">
    
    Add the `Client ID` from *Step 3* of this procedure.
    
    </td>
    <td valign="top">
    
    **Value** of `Client ID`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tokenServiceURL.queries.client\_secret*
    
    </td>
    <td valign="top">
    
    Add the `Client Secret` from *Step 3* of this procedure.
    
    </td>
    <td valign="top">
    
    **Value** of `Client Secret`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-ApplicationKey*
    
    </td>
    <td valign="top">
    
    Add the `API Application Key` value located on the *View Application Keys* page in SAP Fieldglass Configuration Manager.

    This value is used when making calls to the *URL* in this destination.
    
    </td>
    <td valign="top">
    
    **Value** of `API Application Key` 
    
    </td>
    </tr>
    </table>
    
8.  Select the *Use default JDK truststore* checkbox.

9.  Choose *Save*.

10. \(Optional\) To check the connectivity between the SAP Task Center service and SAP Fieldglass, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Fieldglass.


**Related Information**  


[SAP Fieldglass Configuration Manager Guide](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/3e76ca93d2b6423ebbffd4e830ec59e5.html)

