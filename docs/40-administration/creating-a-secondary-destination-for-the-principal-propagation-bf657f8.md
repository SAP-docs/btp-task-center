<!-- loiobf657f8adefa4a468aa3c71783fca291 -->

# Creating a Secondary Destination for the Principal Propagation



<a name="loiobf657f8adefa4a468aa3c71783fca291__prereq_klt_lls_dnb"/>

## Prerequisites

-   You have saved the trust certificate file locally, as described in [Connect SAP SuccessFactors and SAP Task Center](connect-sap-successfactors-and-sap-task-center-eae23f3.md).

-   You have performed the steps described in [Creating the Primary Destination with the Technical User](creating-the-primary-destination-with-the-technical-user-dc5407b.md).




## Procedure

1.  On your SAP SuccessFactors HCM Suite tenant register an OAuth client application:

    1.  Use the properties described in the table below and register an OAuth2 client application, following the procedure in [Registering your OAuth Client Application](https://help.sap.com/viewer/DRAFT/568480cc877d4337992a2cd9792fbfed/latest/en-US/6b3c741483de47b290d075d798163bc1.html).


        <table>
        <tr>
        <th valign="top">

        Property


        
        </th>
        <th valign="top">

        Description


        
        </th>
        <th valign="top">

        Example


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        *Application Name*


        
        </td>
        <td valign="top">

        Enter the unique name of your OAuth client.


        
        </td>
        <td valign="top">

        **Example**:

        ***OneInboxAppPP***


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Application URL*


        
        </td>
        <td valign="top">

        Add here a unique URL, for example the *uaa* \> *url* link from the service key \(see *Step 1* in [Creating the Primary Destination with the Technical User](creating-the-primary-destination-with-the-technical-user-dc5407b.md)\) and append */pp* to the URL.


        
        </td>
        <td valign="top">

        **Example**:

        ***https://inbox-subaccount-name.authentication.eu10.hana.ondemand.com/pp***


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Bind to Users*


        
        </td>
        <td valign="top">

        Disable the binding to users.


        
        </td>
        <td valign="top">

         


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *X.509 Certificate*


        
        </td>
        <td valign="top">

        Add the content from the downloaded trust certificate, between the `-----BEGIN CERTIFICATE-----` and `-----END CERTIFICATE-----` identifiers.


        
        </td>
        <td valign="top">

         


        
        </td>
        </tr>
        </table>
        
    2.  After the OAuth2 client application registration is complete, get the *API key* by following the steps below:

        1.  To preview the new Client Application, select *View* from the *Action* column.

        2.  Copy the *API Key* for principal propagation for later use.

            > ### Note:  
            > The *API key* is only valid for the subaccount that was used to download the trust certificate.



2.  In the SAP BTP cockpit, create and configure an *OAuth2SAMLBearerAssertion* destination:

    1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

    2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *SuccessFactors\_PP*. You can use the sample destination or clone it, and update the properties as described below.

        If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described below.

    3.  Configure the properties of the destination as described in the following table:



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

    For more information about the name of the primary destination, see [Creating the Primary Destination with the Technical User](creating-the-primary-destination-with-the-technical-user-dc5407b.md).

    > ### Note:  
    > If you change the name of the primary destination, you should also update this destination name.


    
    </td>
    <td valign="top">

    **Example**:

    ***SuccessFactors\_PP***


    
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

    Add the URL for your SAP SuccessFactors data center, listed in [About HCM Suite OData APIs](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/03e1fc3791684367a6a76a614a2916de.html), and replace the suffix `/odata/v2/` with `/api-ext/` .


    
    </td>
    <td valign="top">

    **Example**:

    ***https://test-api.lab-rot.ondemand.com/api-ext/***


    
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

    Add `www.successfactors.com` 


    
    </td>
    <td valign="top">

    **Value**:

    ***www.successfactors.com***


    
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

    Add the *API Key* for principal propagation, that you copied is step 1 of this procedure.


    
    </td>
    <td valign="top">

    **Value** of ***API Key***


    
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

    Add a URL using the pattern: `https://<SuccessFactorsTenantAPIURL>/ oauth/token` 


    
    </td>
    <td valign="top">

    **Example**:

    ***https://test-api.lab-rot.ondemand.com/oauth/token***


    
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

    *apiKey*


    
    </td>
    <td valign="top">

    Add the *API Key* for principal propagation, that you copied in step 1 of this procedure.


    
    </td>
    <td valign="top">

    **Value** of ***API Key***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *companyId*


    
    </td>
    <td valign="top">

    Company identifier


    
    </td>
    <td valign="top">

    **Value** of ***SAP SuccessFactors Company ID***


    
    </td>
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

    ***urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified***


    
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

    ***SuccessFactors***


    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.


