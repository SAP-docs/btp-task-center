<!-- loio50ce13335bb4404cb0eddebb37de0855 -->

# Connect SAP S/4HANA Cloud Private Edition and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with on-premise tasks from SAP S/4HANA Cloud Private Edition \(formerly known as SAP S/4HANA Cloud, extended edition\) on SAP BTP, Cloud Foundry environment.



<a name="loio50ce13335bb4404cb0eddebb37de0855__prereq_jrj_4f1_ckb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP S/4HANA Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-s-4hana-integration-scenario?version=Cloud).

-   You have performed the steps in [Prepare SAP Cloud Connector and SAP S/4HANA for the SAP Task Center Connection](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/0f18dddf28764f5b807ecd80549044cc/5c6cf3d9e754468fbd6b3f5073fe085f.html?locale=en-US&version=latest). Choose your SAP S/4HANA Cloud Private Edition version from the dropdown menu next to the documentation title.

    Make sure you save the following information, as you need it for the SAP S/4HANA Cloud Private Edition destination setup:

    -   \(Optional\) *Location ID* from step *Perform the initial configuration of the Cloud Connector and define location ID*

        > ### Note:  
        > *Location ID* is a mandatory property for the creation of the destination only if you have more than one Cloud Connectors in the subaccount.

    -   *Virtual Host* and *Virtual Port* from step *Configure access control in the Cloud Connector for your SAP S/4HANA back-end system*


-   Create a dedicated service instance for SAP Task Center in the Cloud Foundry subaccount, where your initial SAP Task Center instance was created. This enables task updates to be pushed from your ABAP system. Follow the steps in [Create a Service Instance Using the SAP BTP Cockpit](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/dc9af9fd363b4e989af6ff2f19548d32.html?version=Cloud) and create a service key for the service instance. Open the JSON file of the service key and get the following values:

    -   *endpoints* \> *inbox\_rest\_url*
    -   *uaa* \> *url*
    -   *uaa* \> *clientid*
    -   *uaa* \> *clientsecret*

-   You have performed the steps in [Integrating SAP Task Center](https://help.sap.com/viewer/0f18dddf28764f5b807ecd80549044cc/latest/en-US/1da230b82a984cda85d0041e13060a87.html) and have a user name and password for granting access to the task pull service, as described in *Configuring SAP Task Center Integration*.

    Use the SAP Cloud Connector from the previous prerequisite for the step *Tunnel the request using, for example, the Cloud Connector* in [Configuring SAP Task Center Integration](https://help.sap.com/viewer/0f18dddf28764f5b807ecd80549044cc/latest/en-US/5117f21ef28f4e698d99fe3fdbc1be2a.html).

-   You have the client number of your SAP S/4HANA Cloud Private Edition system.

> ### Note:  
> Do not configure more than one destination to the same SAP S/4HANA Cloud Private Edition system for one SAP Task Center. This will result in having duplicate tasks for end users.



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area on the left.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *S4HANACloudPE*. You can use the sample destination or clone it, and update the properties as described below.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described below.

3.  Configure the properties of the destination as follows:


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
    
    Configure a destination name. It can be up to 64 characters long.

    > ### Note:  
    > The name of the destination must not be longer than 64 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.


    
    </td>
    <td valign="top">
    
    **Example**:

    `S4HANACloudPE`
    
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
    
    Create the URL by following the pattern `<Virtual Host>:<Virtual Port>`, using the values you've got when configuring the access control in the SAP Cloud Connector. For more information, see *Prerequisites*.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy type*
    
    </td>
    <td valign="top">
    
    Choose the *OnPremise* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    Choose the *BasicAuthentication* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*
    
    </td>
    <td valign="top">
    
    Add the service user for task pull service. For more information, see *Prerequisites*.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Add the password for the service user for task pull service. For more information, see *Prerequisites*.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID*
    
    </td>
    <td valign="top">
    
    \(Optional\) Provide the *Location ID* that you configured in the initial configuration of the SAP Cloud Connector. For more information, see *Prerequisites*.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
    **Additional Properties:**


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
    
    Enables the SAP Task Center to connect to the configured task provider destination.

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
    
    *tc.clientId*
    
    </td>
    <td valign="top">
    
    This property is used to enable task updates to be pushed from SAP S/4HANA Cloud Private Edition.

    The value of this property is the value of the *uaa* \> *clientid* from the service key of the new service instance \(see *Prerequisites*\).

    > ### Note:  
    > Set this property only when you have completed *Integrating SAP Task Center* from the *Prerequisites* section. If you haven't completed this step, you might not be able to receive tasks from SAP S/4HANA Cloud Private Edition.


    
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
    
    Type of the task provider.
    
    </td>
    <td valign="top">
    
    `S/4HANAPrivateCloud`
    
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

    `SAP S/4HANA Cloud, Private Edition`
    
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

    `SAP S/4HANA Cloud, Private Edition Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP S/4HANA Cloud, Private Edition Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.queries.sap-client*
    
    </td>
    <td valign="top">
    
    The client number of the SAP S/4HANA Cloud Private Edition system.
    
    </td>
    <td valign="top">
    
    **Example**:

    `100`
    
    </td>
    </tr>
    </table>
    
4.  Save your configuration.

5.  Check for the status of the destination in the Task Center Administration app.

    -   If the destination is in state *OK*, then it is ready to be used and you can continue with the next step.
    -   If the destination is in state *Error* with the following error message: "To enable the SAP S/4HANA Cloud, private edition connector for the \[destination name\] destination, you must have created a ticket as per the SAP Task Center documentation.", and you are using the `cloud-only-tasks` or `standard` service plans, then open a ticket through the [SAP Support Portal](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fsupport.sap.com%2F) to get it enabled. Use the **LOD-BPM-INB** component and "SAP S/4HANA Cloud, Private Edition Verification" as subject of the ticket, asking the SAP colleagues to enable your destination. Provide the following information:
        -   name of the destination you just created

        -   your subaccount tenant ID

        -   the region, where your SAP Task Center is hosted \(for example, `eu10`, `ap10`\). You can find the region as part of the *API Endpoint* on the *Overview* page of your subaccount in the SAP BTP cockpit. For more information about regions, see [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).



6.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP S/4HANA Cloud Private Edition, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP S/4HANA Cloud Private Edition.


