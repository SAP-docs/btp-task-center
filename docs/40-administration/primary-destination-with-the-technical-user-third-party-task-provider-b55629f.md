<!-- loiob55629fd92c24244ac8e435e619be178 -->

# Primary Destination with the Technical User \(Third-Party Task Provider\)

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from a third-party task provider.



<a name="loiob55629fd92c24244ac8e435e619be178__prereq_zzy_spz_pjb"/>

## Prerequisites

You have completed the prerequisites, descibed in [Connect a Third-Party Task Provider and SAP Task Center](connect-a-third-party-task-provider-and-sap-task-center-c6362b6.md).

> ### Note:  
> Do not configure more than one destination to the same third-party task provider system for one SAP Task Center. This will result in having duplicate tasks for end users.



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

    `MyThirdParty`
    
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
    
    Use the third-party task provider tenant URL.

    Please, note that SAP Task Center appends additional attributes \(for example, `/task-provider/v2/`\) to this URL.

    The task provider SPI endpoints must be accessible at URL: `{destination.URL}/task-provider/v{version_number}/{endpoint_name}`.

    > ### Note:  
    > If you change the *URL* of an already configured destination that has tasks stored in the `Task Cache`, these tasks will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://sample_task_provider.com/v2`
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Make sure that you also maintain properties such as *Authentication*, so that a valid security token is returned by the destination. This token will be used in the technical user flows,for instance, pulling tasks and task definitions.

    For more information about the authentication methods, see [HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/http-destinations?version=Cloud).

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
    > Without this property, the destination cannot be used by SAP Task Center.

    > ### Note:  
    > Any value other than `true` \(for example `false`\) has the following effects:
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
    
    *tc.pp.cip.token*
    
    </td>
    <td valign="top">
    
    \(Optional\) Add this property in case you are using corporate tokens from a corporate identity provider, configured in Identity Authentication. For more information, see [Include Tokens from Corporate Identity Providers or Identity Authentication in Tokens of the SAP Authorization and Trust Management Service](https://help.sap.com/docs/btp/sap-business-technology-platform/including-tokens-from-corporate-identity-providers-or-identity-authentication-in-tokens-of-sap-authorization-and-trust-management-service?version=Cloud).

    The default value is `false`.
    
    </td>
    <td valign="top">
    
    **Value**:

    `true`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.provider\_type*
    
    </td>
    <td valign="top">
    
    Type of the task provider.
    
    </td>
    <td valign="top">
    
    **Value**:

    `Custom`
    
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

    `Third Party`
    
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

    `Third-Party Task`
    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.

6.  \(Optional\) To check the connectivity between the SAP Task Center service and the third-party task provider, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and the third-party task provider.


