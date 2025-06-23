<!-- loio223b0839635d4679966a4613b670df9a -->

# Connect UiPath and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from UiPath on SAP BTP, Cloud Foundry environment.



<a name="loio223b0839635d4679966a4613b670df9a__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. Make sure you have followed the [Third-Party Scenarios](https://help.sap.com/docs/cloud-identity/system-integration-guide/third-party-integration).

-   You have completed the steps described in the document [Connecting SAP Task Center to UiPath Action Center](https://docs.uipath.com/automation-cloud/automation-cloud/latest/sap/configuring-the-connection#enabling-the-push-of-task-updates) to enable the functionality in UiPath and you have the values of the following properties:

    -   *Task SPI*
    -   *Client Id*
    -   *Client Secret*
    -   *Token Service URL*
    -   *URL.headers.ServiceUrl*


> ### Note:  
> Do not configure more than 1 destination to the same UiPath system for 1 SAP Task Center. This will result in having duplicate tasks for end users.

SAP Task Center supports translatable properties of tasks and task definitions from UiPath only in English.



## Procedure

1.  Create a new service instance to enable task updates to be pushed from UiPath. Follow the steps in [Create a Service Instance Using the SAP BTP Cockpit](../30-initial-setup/create-a-service-instance-using-the-sap-btp-cockpit-dc9af9f.md) and create a service key for the service instance. Open the JSON file of the service key and get the following values:

    -   *endpoints* \> *inbox\_rest\_url*
    -   *uaa* \> *url*
    -   *uaa* \> *clientid*
    -   *uaa* \> *clientsecret*

2.  Follow the steps described in [Connecting SAP Task Center to UiPath Action Center](https://docs.uipath.com/automation-cloud/automation-cloud/latest/sap/configuring-the-connection#enabling-the-push-of-task-updates) to enable task updates to be pushed from UiPath.

3.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> ***Destinations* tab from the navigation area.

4.  Create a new destination and manually add the properties as described in the following table.


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

    `UiPath`
    
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
    
    Add the *Task SPI* from the *Prerequisites* section.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://abc.uipath.com/uipalpsapstge2e/DefaultTenant/bupproxyservice_/orchestrator/api`
    
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
    
    Add the value of the *Client Id* property from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Client Id*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    Add the value of the *Client Secret* property from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Client Secret*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    Add the *Token Service URL* from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://abc.uipath.com/000abc1a-abc1-11a1-1234-a1234ab1a123/identity_/connect/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the *Client Id* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Client Id*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the *Client Secret* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Client Secret*
    
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
    
    *tc.clientId*
    
    </td>
    <td valign="top">
    
    This property is used to enable task updates to be pushed from UiPath.

    The value of this property is the value of the *uaa* \> *clientid* from the service key of the new service instance \(see *Step 1*\).

    > ### Note:  
    > Set this property only when you have enabled task updates to be pushed from UiPath \(see *Step 2*\). If you haven't completed this step, you might not be able to receive tasks from UiPath.


    
    </td>
    <td valign="top">
    
    **Value** of *clientid*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.enabled*
    
    </td>
    <td valign="top">
    
    Enables SAP Task Center to connect to the configured task provider destination.

    > ### Caution:  
    > If you are using the sample destinations created by the booster \(see [Automatic Setup](https://help.sap.com/docs/task-center/sap-task-center/automatic-setup)\), you must add the *tc.enabled* property manually. Without this property, the destination cannot be used by SAP Task Center.

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
    > If you want to delete the task cache and repopulate it for this destination, see [Repopulate the Task Cache](https://help.sap.com/docs/task-center/sap-task-center/repopulate-task-cache).


    
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
    
    Type of the task provider. This property is needed if you want to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](https://help.sap.com/docs/task-center/sap-task-center/configure-filter-tabs-in-sap-task-center-web-app). 
    
    </td>
    <td valign="top">
    
    **Value**:

    `UiPath`
    
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

    You can define a separate property for a filter tab translation for each of the supported languages \(see [Supported Languages](https://help.sap.com/docs/task-center/sap-task-center/supported-languages)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.group* property with the value `<default_translation>` for a default translation of the group name.

    -   the *tc.ui.group.de-DE* property with the value `<German_translation>` for a German translation of the group name.


    For more information, see [Configure Filter Tabs in the SAP Task Center Web App](https://help.sap.com/docs/task-center/sap-task-center/configure-filter-tabs-in-sap-task-center-web-app).
    
    </td>
    <td valign="top">
    
    **Example**:

    `UiPath`
    
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

    You can define a separate property for a task label translation for each of the supported languages \(see [Supported Languages](https://help.sap.com/docs/task-center/sap-task-center/supported-languages)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.label* property with the value `<default_translation>` for a default translation of the label.

    -   the *tc.ui.label.de-DE* property with the value `<German_translation>` for a German translation of the label.


    For more information, see [Configure Labels in SAP Task Center Web App](https://help.sap.com/docs/task-center/sap-task-center/configure-labels-in-sap-task-center-web-app).
    
    </td>
    <td valign="top">
    
    **Example for *tc.ui.label***:

    `SAP UiPath Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP UiPath Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tokenService.body.scope*
    
    </td>
    <td valign="top">
    
    The scope provides SAP Task Center with access to read tasks, created in the UiPath Action Center.
    
    </td>
    <td valign="top">
    
    **Value**:

    `OR.Tasks`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-ApplicationKey*
    
    </td>
    <td valign="top">
    
    Add the *URL.headers.ServiceUrl* value from the *Prerequisites* section.

    This value is used when making calls to the *URL* in this destination.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://abc.uipath.com/uipalpsapstge2e/DefaultTenant/orchestrator_`
    
    </td>
    </tr>
    </table>
    
6.  Select the *Use default JDK truststore* checkbox.

7.  Choose *Save*.

8.  \(Optional\) To check the connectivity between the SAP Task Center service and UiPath, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](https://help.sap.com/docs/task-center/sap-task-center/monitoring).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and UiPath.


**Related Information**  


[Approving automation tasks](https://docs.uipath.com/automation-cloud/automation-cloud/latest/sap/approving-automation-tasks)

