<!-- loio50ce13335bb4404cb0eddebb37de0855 -->

# Connect SAP S/4HANA Cloud, Private Edition and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with on-premise tasks from SAP S/4HANA Cloud, private edition \(formerly known as SAP S/4HANA Cloud, extended edition\) on SAP BTP, Cloud Foundry environment.



<a name="loio50ce13335bb4404cb0eddebb37de0855__prereq_jrj_4f1_ckb"/>

## Prerequisites

-   You have performed the steps in [Prepare SAP Cloud Connector and SAP S/4HANA for the SAP Task Center Connection](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/0f18dddf28764f5b807ecd80549044cc/5c6cf3d9e754468fbd6b3f5073fe085f.html?locale=en-US&version=latest). Choose your SAP S/4HANA Cloud, private edition version from the dropdown menu next to the documentation title.

    > ### Caution:  
    > For the setup of SAP Task Center, you must have a Cloud Connector that uses user UUID as the subject pattern for principal propagation. If you already have a Cloud Connector configuration that uses a different subject pattern \(for example, e-mail\), create a second Cloud Connector with user UUID and use it for the SAP Task Center communication.

    Make sure you save the following information, as you need it for the SAP S/4HANA Cloud, private edition destination setup:

    -   \(Optional\) *Location ID* from step *Perform the initial configuration of the Cloud Connector and define location ID*

        > ### Note:  
        > *Location ID* is a mandatory property for the creation of the destination only if you have more than one Cloud Connectors in the subaccount.

    -   *Virtual Host* and *Virtual Port* from step *Configure access control in the Cloud Connector for your SAP S/4HANA back-end system*


-   You have performed the steps in [SAP Task Center Integration](https://help.sap.com/viewer/0f18dddf28764f5b807ecd80549044cc/latest/en-US/1da230b82a984cda85d0041e13060a87.html) and have a user name and password for granting access to the task pull service, as described in [Create Service User for Task Pull Service](https://help.sap.com/viewer/0f18dddf28764f5b807ecd80549044cc/latest/en-US/229c5a1f659341efa2bb6205159d6209.html).

    Use the SAP Cloud Connector from the previous prerequisite for the step *Tunnel the request using, for example, the Cloud Connector* in [Configuring SAP Task Center Integration](https://help.sap.com/viewer/0f18dddf28764f5b807ecd80549044cc/latest/en-US/5117f21ef28f4e698d99fe3fdbc1be2a.html).

-   You have the client number of your SAP S/4HANA Cloud, private edition system.
-   You have completed all prerequisites listed in [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).


> ### Note:  
> Do not configure more than one destination to the same SAP S/4HANA Cloud, private edition system for one SAP Task Center. This will result in having duplicate tasks for end users.



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
    
    Configure a destination name. It can be up to 16 characters long.

    > ### Note:  
    > The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.


    
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
    
    The client number of the SAP S/4HANA Cloud, private edition system.


    
    </td>
    <td valign="top">
    
    **Example**:

    `100`


    
    </td>
    </tr>
    </table>
    
4.  Save your configuration.

5.  Your SAP S/4HANA Cloud, private edition destination will be initially in *Error* state. To get it enabled, open a ticket through the [SAP Support Portal](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fsupport.sap.com%2F), using the **LOD-BPM-INB** component. Use "SAP S/4HANA Cloud, Private Edition Verification" as subject of the ticket, provide the name of the destination you just created and your subaccount tenant ID, and ask the SAP colleagues to enable your destination.

6.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP S/4HANA Cloud, private edition, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP S/4HANA Cloud, private edition.


