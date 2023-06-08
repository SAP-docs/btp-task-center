<!-- loio2cc8cee1c8fc44888eade975fb8b2284 -->

# Creating a Secondary Destination for the Principal Propagation

Create a secondary SAP Cloud for Customer destination for the principal propagation.



<a name="loio2cc8cee1c8fc44888eade975fb8b2284__prereq_klt_lls_dnb"/>

## Prerequisites

-   You have performed the steps described in [Principal Propagation Flow and Set Up](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/5d50dcbccae9476ab80f911f3a422ef2.html?version=CLOUD).

    You need the following parameters for the setup of the destination:

    -   You have your SAP Cloud for Customer tenant *URL*.

    -   *Audience*

        You have perfomed the steps in [Obtain Local Service Provider Value](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/5d50dcbccae9476ab80f911f3a422ef2.html?version=CLOUD#obtain-local-service-provider-value) and have the *Audience* value.

    -   *Client ID* and *Client Secret*

        You have performed the steps in [Register OAuth Client in SAP Cloud For Customer](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/5d50dcbccae9476ab80f911f3a422ef2.html?version=CLOUD#register-oauth-client-in-sap-cloud-for-customer) and have the client ID and secret.


-   You have performed the steps described in [Creating the Primary Destination with the Technical User](creating-the-primary-destination-with-the-technical-user-bb3728b.md). You need the exact name of the primary destination.




## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

2.  Create a new destination and manually add the properties as described below.


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
    
        The destination name for the principal propagation must be the same as the name of the primary destination for the technical user with the suffix ***\_PP***.

    For more information about the name of the primary destination, see [Creating the Primary Destination with the Technical User](creating-the-primary-destination-with-the-technical-user-bb3728b.md).

    > ### Note:  
    > If you change the name of the primary destination, you should also update this destination name.


    
    </td>
    <td valign="top">
    
        **Example**:

    ***C4C\_PP***


    
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
    
        Add the *URL* from *Prerequisites*.


    
    </td>
    <td valign="top">
    
        **Example**:

    ***https://example.sapbydesign.com***


    
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
    
        Add the *Audience* from *Prerequisites*.

    > ### Note:  
    > Make sure you copy exactly this value, as it is case sensitive.


    
    </td>
    <td valign="top">
    
        **Example**:

    ***HTTPS://example.sapbydesign.com***


    
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

    ***urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession***


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *Client Key*


    
    </td>
    <td valign="top">
    
        Add the *Client ID* from *Prerequisites*.


    
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
    
        Add the **URL** value from the *Prerequisites* and append ***/sap/bc/sec/oauth2/token*** to it, following the pattern `https://<C4CTenantAPIURL>/sap/bc/sec/oauth2/token`.


    
    </td>
    <td valign="top">
    
        **Example**:

    ***https://example.sapbydesign.com/sap/bc/sec/oauth2/token***


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *Token Service User*


    
    </td>
    <td valign="top">
    
        Add the *Client ID* from *Prerequisites*.


    
    </td>
    <td valign="top">
    
         


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *Token Service Password*


    
    </td>
    <td valign="top">
    
        Add the *Client Secret* from *Prerequisites*.


    
    </td>
    <td valign="top">
    
         


    
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
    
        *nameIdFormat*


    
    </td>
    <td valign="top">
    
        Value of the `NameIdFormat` tag, which is part of the generated `OAuth2SAMLBearerAssertion` authentication.


    
    </td>
    <td valign="top">
    
        **Value**:

    urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *scope*


    
    </td>
    <td valign="top">
    
        The scope is defined while registering the OAuth client in [Register OAuth Client in SAP Cloud For Customer](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/5d50dcbccae9476ab80f911f3a422ef2.html?version=CLOUD#register-oauth-client-in-sap-cloud-for-customer).


    
    </td>
    <td valign="top">
    
        **Value**:

    UIWC:CC\_HOME


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *tc.provider\_type*


    
    </td>
    <td valign="top">
    
        Type of the task provider. This property is needed if you would like to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md). 


    
    </td>
    <td valign="top">
    
        **Value**:

    ***C4C***


    
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

    -   the *tc.ui.group* property with the value ***<default\_translation\>*** for a default translation of the group name.

    -   the *tc.ui.group.de-DE* property with the value ***<German\_translation\>*** for a German translation of the group name.


    For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md).


    
    </td>
    <td valign="top">
    
        **Example**:

    ***SAP Cloud for Customer***


    
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

    -   the *tc.ui.label* property with the value ***<default\_translation\>*** for a default translation of the label.

    -   the *tc.ui.label.de-DE* property with the value ***<German\_translation\>*** for a German translation of the label.


    For more information, see [Configure Labels in SAP Task Center Web App](configure-labels-in-sap-task-center-web-app-a0be9ad.md).


    
    </td>
    <td valign="top">
    
        **Example for *tc.ui.label***:

    ***SAP Cloud for Customer Task***

    **Example for *tc.ui.label.de-DE***:

    ***SAP Cloud for Customer Aufgabe***


    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.


