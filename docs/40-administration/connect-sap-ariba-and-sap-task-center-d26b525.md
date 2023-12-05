<!-- loiod26b525d88574afdae98428d65f26fd9 -->

# Connect SAP Ariba and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP Ariba on SAP BTP, Cloud Foundry environment.



<a name="loiod26b525d88574afdae98428d65f26fd9__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP Ariba Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-ariba-integration-scenario).

-   You have an existing SAP Ariba tenant and know your SAP Ariba `realm name` or `customer site name`. For more information, see [How do I find out my realm name?](https://support.ariba.com/item/view/KB0395389).

-   For the integration with SAP Ariba Sourcing you must have completed the steps described in [How to enable SAP Task Center for SAP Ariba Sourcing in the SAP S/4HANA Cloud 4BL and 4QN Integrations Scenarios](https://help.sap.com/docs/ARIBA_SOURCING/b6d46a2e6c3043d7bb0cbabba4262560/18bd32b6058d4e47a4f920ed115599e1.html) to enable the functionality in SAP Ariba.
-   For the integration with SAP AribaBuying, see [SAP Task Center for SAP Ariba Buying](https://help.sap.com/docs/ARIBA_PROCUREMENT/27d44834e9164377b324539985725ecd/c80239e20d3a46bd9577f035224b7ff1.html) and contact your SAP Ariba Technical Support to enable the functionality in SAP Ariba.

> ### Note:  
> Do not configure more than one destination to the same SAP Ariba system for one SAP Task Center. This will result in having duplicate tasks for end users.



<a name="loiod26b525d88574afdae98428d65f26fd9__context_bkf_t2z_jrb"/>

## Context

The SAP Ariba entity may have SAP AribaBuying, SAP AribaSourcing, or both products. You have to create separate destinations for each product \(SAP AribaBuying and SAP AribaSourcing\). The *URL* specifies whether the destination is for SAP AribaBuying or SAP AribaSourcing.



## Procedure

1.  On the SAP Ariba Developer Portal create an application for each product you want to use \(SAP AribaBuying, SAP AribaSourcing, or create two applications if you want to use both\). Contact SAP Ariba Technical Support and provide the `application key`, `realm name` and share the SAP Ariba product it needs to link to. Follow these steps:

    1.  Create an application and generate the application key for each SAP Ariba product you would like to connect, following the steps at [Creating an Application on the SAP Ariba Developer Portal](https://help.sap.com/docs/ARIBA_APIS/b61dd8c7e22c4fe489f191f66b4c48d6/496d221506e941a894237243ca9ddf2a.html).
    2.  Save the application key for each created application.
    3.  Note each *URL* and *Token Service URL* for the SAP Task Center SPI. You need this information when creating the destination.

        Request separate applications for the destinations for SAP AribaBuying and SAP AribaSourcing:

        -   For SAP Ariba Buying request the *URL* for the *Procurement SPI for SAP Task Center*.

        -   For SAP Ariba Sourcing request the *URL* for the *Sourcing SPI for SAP Task Center*.


        The *Token Service URL* is the same for both SAP AribaBuying and SAP AribaSourcing.

    4.  To request the activation of the application on the SAP Ariba Developer Portal, please create a Service Request with SAP Ariba Support and provide the following information to the SAP Ariba Technical Support:
        -   The *Application key* of the application, created on the SAP Ariba Developer Portal

        -   The product that the request is for \(SAP AribaBuying or SAP Ariba Sourcing\)

        -   `Realm name`

        -   The data center where your SAP Ariba `realm` resides


    5.  To request IDP registration on the SAP Ariba OAuth, create a Service Request and provide the following information to the SAP Ariba Technical Support:
        -   Your SAP Ariba `realm name` or `customer site name` \(see *Prerequisites*\)
        -   Entity Identifier \(`entityID`\) in the SAML assertion request

            The `entityID` is sent by the destination service and must be in the following format:

            `cfapps.${S1_LANDSCAPE_DOMAIN}/${S1_SUBACCOUNT_ID}`.

            For example, `cfapps.sap.hana.ondemand.com/abcd1234-ab12-ab12-ab12-abcd1234abcd1234`.

            For more information, see [User Propagation between Cloud Foundry Applications](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/8ebf60c82a8e4cfc904f441c0c0acd6b.html).

        -   The destination service certificate

            To get the destination service certificate, log on to your Cloud Foundry subaccount, select the *Destinations* tab from the navigation area, and choose *Download Trust* to download the destination service certificate.

            > ### Caution:  
            > Make sure to renew your trust certificate before it expires. For the time while you are renewing the trust certificate and updating it on the task provider systems you may not be able to work on tasks, nor receive task updates.
            > 
            > For more information, see [Renew Destination Trust Certificates](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/8080abf7d2cf4918802aa86e955ffc8b.html#renew-destination-trust-certificates).

        -   Your Ariba Network ID \(ANID or NetworkId\)

            You can find it in your Company Profile. For more information, see [SAP Ariba Glossary](https://help.sap.com/viewer/19025eff298741f78ecfff03d35e9331/cloud/en-US) and [How to specify your company profile information](https://help.sap.com/viewer/5c0bdb0caa3042a288b3a1fb83b2fb1e/cloud/en-US/dd7e8953f0181014846b9461fdc68461.html).



2.  When the application is set up with SPIs on your SAP Ariba developer portal, follow the steps described in [How to generate the OAuth Secret and Base64 Encoded Client and secret](https://help.sap.com/viewer/b61dd8c7e22c4fe489f191f66b4c48d6/cloud/en-US/81f493759bbb42e5b7486bfdf8185fa3.html) to generate the `OAuth secret`. You need the following values to complete the setup:

    -   `Oauth client ID`
    -   `OAuth secret`
    -   `Application key`

3.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area.

4.  If you have executed the automatic setup \(see [Automatic Setup](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/3a499676e7ae4282af84092f778e3737.html)\), you already have a sample destination called *Ariba*. You can use the sample destination or clone it, and update the properties as described below.

    If you have followed the manual setup \(see [Manual Setup](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/0f00d3d3e2ab460c856d409c469fb4f1.html)\), you have to create a new destination and manually add the properties as described next.

5.  Configure the properties of the destination as described next:


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
    > The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.

    > ### Note:  
    > If you change the *name* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `Ariba`
    
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
    
    Enter the appropriate *URL*.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Examples**:

    -   For SAP AribaBuying:

        `https://openapi.ariba.com/api/procurement-task-provider/v2/prod`

    -   For SAP AribaSourcing:

        `https://openapi.ariba.com/api/sourcing-task-provider/v1/prod`



    
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
    
    The *Audience* is used to construct the SAML assertion. Its value should be `Ariba`.
    
    </td>
    <td valign="top">
    
    **Value**:

    `Ariba`
    
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
    
    Add the *Application key* value.
    
    </td>
    <td valign="top">
    
    **Value** of `Application key` \(one for each solution\)
    
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
    
    Add the *Token Service URL*.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://api.ariba.com/v2/oauth/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    Add the value of the *OAuth client ID*.
    
    </td>
    <td valign="top">
    
    **Value** of `OAuth client ID`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    Add the value of the *OAuth secret*.
    
    </td>
    <td valign="top">
    
    **Value** of `OAuth secret`
    
    </td>
    </tr>
    </table>
    
6.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    > If you are using the sample destinations created by the booster \(see [Automatic Setup](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/3a499676e7ae4282af84092f778e3737.html)\), you must add the *tc.enabled* property manually. Without this property, the destination cannot be used by SAP Task Center.

    > ### Note:  
    > Any value other than `true` \(for example `false`\) will have the following effects:
    > 
    > -   The previously stored tasks are kept in the task cache.
    > 
    > -   The tasks from this destination are **not** displayed in the SAP Task Center Web app.
    > 
    > -   The task cache is not updated with tasks from this destination.
    > 
    > 
    > If you want to delete the task cache and repopulate it for this destination, see [Repopulate the Task Cache](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/e93aa718721444f7aa7e8385a3253a41.html).


    
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
    
    Type of the task provider. This property is needed if you would like to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/53157da9e7ed498ea6b30298bf7d5213.html). 
    
    </td>
    <td valign="top">
    
    **Value**:

    `Ariba`
    
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

    `SAP Ariba`
    
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

    .
    
    </td>
    <td valign="top">
    
    **Example for *tc.ui.label***:

    `SAP Ariba Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Ariba Aufgabe`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tokenServiceURL.headers.apikey*
    
    </td>
    <td valign="top">
    
    Add the value of the *Application key*.

    This value is used when making calls to the *Token service URL* in this destination.
    
    </td>
    <td valign="top">
    
    **Value of** `Application key`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.headers.apikey*
    
    </td>
    <td valign="top">
    
    Add the value of the *Application key*.

    This value is used when making calls to the *URL* in this destination.
    
    </td>
    <td valign="top">
    
    **Value of** `Application key`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL.queries.realm*
    
    </td>
    <td valign="top">
    
    Add the value of the `realm name`.

    This value is used when making calls to the *URL* in this destination.
    
    </td>
    <td valign="top">
    
    **Value** of `your SAP Ariba realm name`
    
    </td>
    </tr>
    </table>
    
7.  Make sure that the default JDK truststore is selected.

8.  Choose *Save*.

9.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP Ariba, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](https://help.sap.com/viewer/08cbda59b4954e93abb2ec85f1db399d/Prod/en-US/9b30be76f14f48c5a72dd7ed7e9babe0.html).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Ariba.


**Related Information**  


[Help for the SAP Ariba developer portal](https://help.sap.com/docs/ariba-apis/help-for-sap-ariba-developer-portal/help-for-sap-ariba-developer-portal)

