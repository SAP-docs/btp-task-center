<!-- loio2fef2f526d4f4d4faaddaaff047816db -->

# Secondary Destination for the Principal Propagation \(SAP Field Service Management\)



<a name="loio2fef2f526d4f4d4faaddaaff047816db__prereq_klt_lls_dnb"/>

## Prerequisites

-   You have performed the steps described in [Primary Destination with the Technical User \(SAP Field Service Management\)](primary-destination-with-the-technical-user-sap-field-service-management-5495960.md).




## Procedure

1.  In the SAP BTP cockpit, create and configure an *OAuth2SAMLBearerAssertion* destination:

    1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

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
    
    The destination name for the principal propagation must be the same as the name of the primary destination for the technical user with the suffix `_PP`.

    For more information about the name of the primary destination, see [Primary Destination with the Technical User \(SAP Field Service Management\)](primary-destination-with-the-technical-user-sap-field-service-management-5495960.md).

    > ### Note:  
    > If you change the name of the primary destination, you should also update this destination name.


    
    </td>
    <td valign="top">
    
    **Example**:

    `FSM_PP`
    
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
    
    Add the value of *SAML metadata* from the *Prerequisites* section in [Connect SAP Field Service Management and SAP Task Center](connect-sap-field-service-management-and-sap-task-center-4a61a25.md).
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://de.fsm.cloud.sap/api/oauth2/v2/saml/saml-test/metadata`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *AuthnContextClassRef*
    
    </td>
    <td valign="top">
    
    Add as value `urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession`
    
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
    
    Add the *API Key* for principal propagation, that you copied is step 1 of this procedure.
    
    </td>
    <td valign="top">
    
    **Value** of `API Key`
    
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
    
    *tc.provider\_type*
    
    </td>
    <td valign="top">
    
    Type of the task provider. This property is needed if you would like to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md). 
    
    </td>
    <td valign="top">
    
    **Value**:

    `FSM`
    
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

    `654321`
    
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

    `1.0`
    
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

    `123456`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *userIdSource*
    
    </td>
    <td valign="top">
    
    Provides information about the `userIdSource`to SAP Cloud Identity Services - Identity Authentication.
    
    </td>
    <td valign="top">
    
    **Value**:

    `email`
    
    </td>
    </tr>
    </table>
    
3.  Select the *Use default JDK truststore* checkbox.

4.  Choose *Save*.


