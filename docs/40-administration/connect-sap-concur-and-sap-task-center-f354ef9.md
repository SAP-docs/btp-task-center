<!-- loiof354ef9cab4641219fd849102d1b5b0c -->

# Connect SAP Concur and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP Concur on SAP BTP, Cloud Foundry environment.



<a name="loiof354ef9cab4641219fd849102d1b5b0c__prereq_zzy_spz_pjb"/>

## Prerequisites

> ### Tip:  
> ![](../30-initial-setup/images/28x28_launch_png_2484bce.png) See also the step-by-step mission for the setup of connection to SAP Concur at [Integrate Your SAP Concur Tasks Into SAP Task Center](https://discovery-center.cloud.sap/missiondetail/3883/3962/).

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP Concur Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-concur-integration-scenario).

-   You have an existing SAP Concur entity, and have generated the `Company Request Token` and `Company UUID`. For more information, see [SAP Concur Company Request Token](https://help.sap.com/docs/SAP_CONCUR/384ace1050b34555a6fed7ad1e49e2eb/1b9049306caf101495ce810462271ffb.html).

    If you need any additional information, contact your SAP Concur implementation consultant.

-   You have enabled the workflows for Concur Expense, Concur Request, or both, for SAP Task Center. For more information, see [SAP Task Center Integration with Concur Solutions](https://help.sap.com/docs/SAP_CONCUR/384ace1050b34555a6fed7ad1e49e2eb/1b9360de6caf1014a1c2f9558d278c18.html).

-   You have opened a ticket to verify your Data Privacy Agreement version.

    To verify if you have the latest Data Privacy Agreement version, please open a ticket through the [SAP Support Portal](https://support.sap.com/), using the **BNS-CON-TSK** component. Use "SAP Concur DPA Version Verification" as subject of the ticket and ask the SAP colleagues to verify your Data Privacy Agreement version. If you don’t have the latest version, you will be prompted to sign a new Data Privacy Agreement and send it back via the ticket.


> ### Note:  
> Do not configure more than one destination to the same SAP Concur entity or product combination for one SAP Task Center. This will result in having duplicate tasks for end users.



<a name="loiof354ef9cab4641219fd849102d1b5b0c__context_tz2_lqw_2nb"/>

## Context

The SAP Concur entity may have Concur Expense, Concur Request, or both products. You have to create separate destinations for each product \(Concur Expense and Concur Request\). The *URL* specifies whether the destination is for Concur Expense or Concur Request. Each destination should have a unique combination of the fields *URL* and *Client Key*.



## Procedure

1.  Navigate to the Cloud Foundry subaccount where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area.

2.  If you have executed the automatic setup \(see [Automatic Setup](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/3a499676e7ae4282af84092f778e3737.html)\), you already sample destinations called *Concur\_req* and *Concur\_exp*. You can use the sample destinations or clone them, and update the properties as described in the following table.

    If you have followed the manual setup \(see [Manual Setup](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/0f00d3d3e2ab460c856d409c469fb4f1.html)\), you have to create a new destination and manually add the properties as described in the following table.

3.  Configure the properties of the destination as described next:


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
    > Note that the name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.
    > 
    > > ### Note:  
    > > If you change the *name* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `Concur_Request`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Choose *HTTP*.
    
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
    
    Enter the appropriate URL:

    -   For travel requests: `https://<datacenter_base_URI>/travelrequest`

    -   For expense reports: `https://<datacenter_base_URI>/expensereports`


    For the full list of SAP Concur datacenter base URIs, contact your SAP Concur implementation consultant.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Examples**:

    -   For travel requests:

        `https://us2.api.concursolutions.com/travelrequest`

    -   For expense reports:

        `https://us2.api.concursolutions.com/expensereports`



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
    </td>
    <td valign="top">
    
    Choose *Internet*.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    Choose *OAuth2SAMLBearerAssertion*.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Audience*
    
    </td>
    <td valign="top">
    
    Used to construct the SAML assertion. Its value should be `Concur`.
    
    </td>
    <td valign="top">
    
    **Value**:

    `Concur`
    
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
    
    Add the `Company Request Token` you have created in the *Prerequisites* section.

    This value is automatically replaced with a `refresh token` after a communication exchange between SAP Concur and SAP Task Center.
    
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
    
    Enter the appropriate URL: `https://<datacenter_base_URI>/oauth2/v0/token`

    For the full list of SAP Concur datacenter base URIs, contact your SAP Concur implementation consultant.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://us2.api.concursolutions.com/oauth2/v0/token`
    
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
    
    *tc.enabled*
    
    </td>
    <td valign="top">
    
    Enables SAP Task Center to connect to the configured task provider destination.

    > ### Caution:  
    > If you are using the sample destinations created by the booster \(see [Automatic Setup](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/3a499676e7ae4282af84092f778e3737.html)\), you must add the *tc.enabled* property manually. Without this property, the destination cannot be used by SAP Task Center.

    > ### Note:  
    > Any value other than `true` \(for example `false`\) has the following effects:
    > 
    > -   The previously stored tasks are kept in the task cache.
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
    
    *tc.concur.auth.req.token.enabled*
    
    </td>
    <td valign="top">
    
    The initial value should be `true`.

    This value is automatically changed to *false* after a communication exchange between SAP Concur and SAP Task Center regarding the `Client Key`.

    > ### Caution:  
    > Changing the property manually after it was set to *false* by SAP Task Center can break the connection to the SAP Concur destination.


    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.concur.dc*
    
    </td>
    <td valign="top">
    
    Corresponds to the data center, where this SAP Concur destination is located \(see your `URL` parameter\).

    Valid values are `eu2` and `us2`.
    
    </td>
    <td valign="top">
    
    **Example**:

    `eu2`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.concur.companyUUID*
    
    </td>
    <td valign="top">
    
    Add the value of `Company UUID` you have created in the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Value of** `Company UUID`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.grant\_type*
    
    </td>
    <td valign="top">
    
    Set this property to `refresh_token`.

    This property enables SAP Task Center to use the `refresh token` maintained in the *Client Key* property.
    
    </td>
    <td valign="top">
    
    **Value**: `refresh_token`
    
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
    
    Type of the task provider. This property is needed if you want to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/53157da9e7ed498ea6b30298bf7d5213.html). 
    
    </td>
    <td valign="top">
    
    **Value**:

    `Concur`
    
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

    You can define a separate property for a filter tab translation for each of the supported languages \(see [Supported Languages](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/c66c693eab8c4e1aa47bddb5ce148348.html)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.group* property with the value `<default_translation>` for a default translation of the group name.

    -   the *tc.ui.group.de-DE* property with the value `<German_translation>` for a German translation of the group name.


    For more information, see [Configure Filter Tabs in the SAP Task Center Web App](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/53157da9e7ed498ea6b30298bf7d5213.html).
    
    </td>
    <td valign="top">
    
    **Example**:

    `SAP Concur`
    
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

    You can define a separate property for a task label translation for each of the supported languages \(see [Supported Languages](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/c66c693eab8c4e1aa47bddb5ce148348.html)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.label* property with the value `<default_translation>` for a default translation of the label.

    -   the *tc.ui.label.de-DE* property with the value `<German_translation>` for a German translation of the label.


    For more information, see [Configure Labels in SAP Task Center Web App](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/a0be9ad5cd7146fca3ac29b92ab631dc.html).
    
    </td>
    <td valign="top">
    
    **Example for *tc.ui.label***:

    `SAP Concur Request Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Concur Request Aufgabe`
    
    </td>
    </tr>
    </table>
    
5.  Select the *Use default JDK truststore* checkbox.

6.  Choose *Save*.

7.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP Concur, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/9b30be76f14f48c5a72dd7ed7e9babe0.html).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Concur.


