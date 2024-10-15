<!-- loio223b0839635d4679966a4613b670df9a -->

# Connect UiPath and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from UiPath on SAP BTP, Cloud Foundry environment.



<a name="loio223b0839635d4679966a4613b670df9a__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. Make sure you have followed the [Third-Party Scenarios](https://help.sap.com/docs/cloud-identity/system-integration-guide/third-party-integration).

-   You have completed the steps described in the document [Connecting SAP Task Center to UiPath Action Center](https://docs.uipath.com/automation-cloud/automation-cloud/latest/sap/configuring-the-connection) to enable the functionality in UiPath and you have the values of the following properties:

    -   *Task SPI Details URL*
    -   *Task SPI Details - URL.headers.ServiceUrl*
    -   *Access Token - Client ID*
    -   *Access Token - Client Secret*
    -   *Access Token - Token Service URL*
    -   *Access Token - Arc Values*


> ### Note:  
> Do not configure more than 1 destination to the same UiPath system for 1 SAP Task Center. This will result in having duplicate tasks for end users.

SAP Task Center supports translatable properties of tasks and task definitions from UiPath only in English.



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> ***Destinations* tab from the navigation area.

2.  Create a new destination and manually add the properties as described in the following table.


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
    > The name of the destination must not be longer than 16 characters, otherwise, the status of the respective SAP Task Center connector will be set to `Error`.

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
    
    Add the *Task SPI Details URL* from the *Prerequisites* section.

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
    
    Add the value of the *Access Token - Client ID* property from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Access Token - Client ID*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    Add the value of the *Access Token - Client Secret* property from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Access Token - Client Secret*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    Add the *Access Token - Token Service URL* from the *Prerequisites* section.
    
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
    
    Add the *Access Token - Client ID* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Access Token - Client ID*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the *Access Token - Client Secret* value from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value** of *Access Token - Client Secret*
    
    </td>
    </tr>
    </table>
    
3.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
    *tokenService.body.acr\_values*
    
    </td>
    <td valign="top">
    
    Add the *Access Token - Arc Values* from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    tenant:12a12345-12a1-123a-1a1a-a12a12ab1234
    
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

    `OR.Tasks.Read`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-ApplicationKey*
    
    </td>
    <td valign="top">
    
    Add the *Task SPI Details - URL.headers.ServiceUrl* value from the *Prerequisites* section.

    This value is used when making calls to the *URL* in this destination.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://abc.uipath.com/uipalpsapstge2e/DefaultTenant/orchestrator_`
    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.

6.  \(Optional\) To check the connectivity between the SAP Task Center service and UiPath, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](https://help.sap.com/docs/task-center/sap-task-center/monitoring).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and UiPath.


**Related Information**  


[Approving automation tasks](https://docs.uipath.com/automation-cloud/automation-cloud/latest/sap/approving-automation-tasks)

