<!-- loio54959605631841b0a47e14225cdc1f16 -->

# Primary Destination with the Technical User \(SAP Field Service Management\)



<a name="loio54959605631841b0a47e14225cdc1f16__prereq_r2r_3ls_dnb"/>

## Prerequisites

-   You have completed the prerequisites section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md) and have the values of the listed parameters.




## Procedure

1.  In the SAP BTP cockpit, create and configure an *OAuth2ClientCredentials* destination:

    1.  Navigate to the Cloud Foundry subaccount where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

    2.  Create a new destination and manually add the properties as follows:



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
    
    The destination name can have up to 64 characters.

    > ### Note:  
    > -   The name of the destination must not be longer than 64 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.
    > 
    > -   If you change the *name* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.
    > 
    > -   If you change this destination name, you should also update the destination name for the principal propagation.


    
    </td>
    <td valign="top">
    
    **Example**:

    `FSM`
    
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
    
    Add the value of *FSM cluster url* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://eu.fsm.cloud.sap/cloud-approval-service/api`
    
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
    
    Add the value of *Client ID* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    Add the value of *Client Secret* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    
     
    
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
    
    Create the *Token Service URL* value from the *FSM cluster url*, following the pattern:

    `https://{cluster}.fsm.cloud.sap/api/oauth2/v2/token`
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://eu.fsm.cloud.sap/api/oauth2/v2/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the value of *Client ID* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    

    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the value of *Client Secret* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    
     
    
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

    `FSM`
    
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

    `SAP Field Service Management`
    
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

    `SAP Field Service Management Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Field Service Management Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-Account-ID*
    
    </td>
    <td valign="top">
    
    Add the value of *FSM account ID* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    654321
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-Client-Id*
    
    </td>
    <td valign="top">
    
    Add `sap-task-center` as value.
    
    </td>
    <td valign="top">
    
    **Value**:

    `sap-task-center`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-Client-Version*
    
    </td>
    <td valign="top">
    
    Add `1.0` as value.
    
    </td>
    <td valign="top">
    
    **Value**:

    1.0
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.X-Company-ID*
    
    </td>
    <td valign="top">
    
    Add the value of *FSM company ID* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    123456
    
    </td>
    </tr>
    </table>
    
3.  Select the *Use default JDK truststore* checkbox.

4.  Choose *Save*.

5.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP Field Service Management, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Field Service Management.


