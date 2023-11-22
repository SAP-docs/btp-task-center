<!-- loio18b3848110be43828b549c81a753821e -->

# Connect SAP Marketing Cloud and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP Marketing Cloud on SAP BTP, Cloud Foundry environment.



<a name="loio18b3848110be43828b549c81a753821e__prereq_ytw_hdv_bpb"/>

## Prerequisites

-   You have performed the steps in [Integrating SAP Task Center](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/0fdb31ce0dff4537a1ac6f98d4d34dbd.html). To complete the setup of this destination, you need the following parameters from [Create a Communication Arrangement](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/913ff1a47a6447e3b7bee17fa6f275ff.html):

    -   *Service URL/Service Interface* that you can find when creating a communication arrangement.

    -   *SAML2 Audience*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *Client ID*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *Token Service URL*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *User Name*, that you have created for the technical communication user..
    -   *Password*, that you have created for the technical communication user.

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).


> ### Note:  
> Do not configure more than one destination to the same SAP Marketing Cloud system for one SAP Task Center. This will result in having duplicate tasks for end users.



<a name="loio18b3848110be43828b549c81a753821e__steps_a5w_hdv_bpb"/>

## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area on the left.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *SMC*. You can use the sample destination or clone it, and update the properties as described below.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described below.

3.  Configure the properties of the destination as described below:


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

    `SMC`
    
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
    
    **Example**:

    `SAP Marketing Cloud Connector`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    Add the *Service URL/Service Interface* value, and remove

    `sap/opu/odata4/sap/api_task_spi_replication/default/sap/api_task_spi_replication/0001/?sap-client=100`

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://example-api.s4hana.ondemand.com/`
    
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
    
    Add the *SAML2 Audience*, that you copied in the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://example.s4hana.ondemand.com`
    
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

    `urn:oasis:names:tc:SAML:2.0:ac:classes:X509`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Key*
    
    </td>
    <td valign="top">
    
    Add the *Client ID*, that you copied in the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `COM501SID100`
    
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
    
    Add the *Token Service URL*, that you copied in the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://example-api.s4hana.ondemand.com/sap/bc/sec/oauth2/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the *User Name*, that you copied in the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `COM501SID100`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the *Password*, that you copied in the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
    **Additional Properties**

    Use the *New Property* button to manually create the following additional properties:


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
    
    Type of the task provider.
    
    </td>
    <td valign="top">
    
    **Value**:

    `SMC`
    
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
    
    `SAP Marketing Cloud`
    
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

    `SAP Marketing Cloud Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Marketing Cloud Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.queries.sap-client*
    
    </td>
    <td valign="top">
    
    The client number of the SAP Marketing Cloud system.
    
    </td>
    <td valign="top">
    
    **Example**:

    `100`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *userIdSource*
    
    </td>
    <td valign="top">
    
    Assertion attribute configured in Identity Authentication and used for user authentication.
    
    </td>
    <td valign="top">
    
    **Value**:

    user\_uuid
    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Save your configuration.

6.  Perform the steps described in [SAP Task Center](https://help.sap.com/docs/SAP_MARKETING_CLOUD/0f9408e4921e4ba3bb4a7a1f75f837a7/b40035cc27a74eb7abe9018a9123db3e.html).

7.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP Marketing Cloud, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Marketing Cloud.


