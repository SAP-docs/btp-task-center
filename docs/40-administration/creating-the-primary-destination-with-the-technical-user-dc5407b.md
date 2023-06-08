<!-- loiodc5407b42c7e435b8124ee7a0816249c -->

# Creating the Primary Destination with the Technical User



<a name="loiodc5407b42c7e435b8124ee7a0816249c__prereq_r2r_3ls_dnb"/>

## Prerequisites

You have saved the trust certificate file locally, as described in [Connect SAP SuccessFactors and SAP Task Center](connect-sap-successfactors-and-sap-task-center-eae23f3.md).



## Procedure

1.  Create a new service instance to enable task updates to be pushed from SAP SuccessFactors. Follow the steps in [Create a Service Instance Using the SAP BTP Cockpit](../30-initial-setup/create-a-service-instance-using-the-sap-btp-cockpit-dc9af9f.md) and create a service key for the service instance. Open the JSON file of the service key and get the following values:

    -   *endpoints* \> *inbox\_rest\_url*
    -   *uaa* \> *url*
    -   *uaa* \> *clientid*
    -   *uaa* \> *clientsecret*

2.  Follow the steps described in [Enabling Push of Task Updates to SAP Task Center](https://help.sap.com/viewer/568480cc877d4337992a2cd9792fbfed/latest/en-US/f65742cc51034ae595c3e0c688418944.html) to enable task updates to be pushed from SAP SuccessFactors.

3.  On your SAP SuccessFactors HCM Suite tenant register an OAuth client application:

    1.  Use the properties described in the table below and register an OAuth2 client application, following the procedure in [Registering your OAuth2 Client Application](https://help.sap.com/viewer/568480cc877d4337992a2cd9792fbfed/latest/en-US/6b3c741483de47b290d075d798163bc1.html).


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
        
                *Application Name*


        
        </td>
        <td valign="top">
        
                Enter the unique name of your OAuth client.


        
        </td>
        <td valign="top">
        
                **Example**:

        ***OneInboxApp***


        
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
        
                *Application URL*


        
        </td>
        <td valign="top">
        
                Add here a unique URL, for example the *uaa* \> *url* link from the service key. See *Step 1*.


        
        </td>
        <td valign="top">
        
                **Example**:

        ***https://inbox-subaccount-name.authentication.eu10.hana.ondemand.com***


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
                *Bind to Users*


        
        </td>
        <td valign="top">
        
                Enable the binding to users.


        
        </td>
        <td valign="top">
        
                 


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
                *User IDs*


        
        </td>
        <td valign="top">
        
                This user is created when you enable the SAP SuccessFactors integration with SAP Task Center. For more information, see [Enabling To-Do Task Integration Between SAP SuccessFactors and SAP Task Center](https://help.sap.com/viewer/568480cc877d4337992a2cd9792fbfed/latest/en-US/c15f23f6f4e24ddea84d5be8e6b935ae.html).


        
        </td>
        <td valign="top">
        
                **Value** of ***TECHNICAL\_USER\_INBOX\_CEF979F3***


        
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
        
    2.  After the OAuth2 client application registration is complete, get the *API key*:

        1.  To preview the new Client Application, select *View* from the *Action* column.

        2.  Copy the *API Key* for the technical user for later use.

            > ### Note:  
            > The *API key* is only valid for the subaccount that was used to download the trust certificate.



4.  In the SAP BTP cockpit, create and configure an *OAuth2SAMLBearerAssertion* destination:

    1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

    2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), then you already have a sample destination called *SuccessFactors*. You can use the sample destination or clone it, and update the properties as described below.

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
    
        The destination name can have up to 16 characters.

    > ### Note:  
    > -   The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to ***Error***.
    > 
    > -   If you change the *name* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.
    > 
    > -   If you change this destination name, you should also update the destination name for the principal propagation.


    
    </td>
    <td valign="top">
    
        **Example**:

    ***SuccessFactors***


    
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
    
        Add the URL for your SAP SuccessFactors data center, listed in [About HXM Suite OData APIs](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/03e1fc3791684367a6a76a614a2916de.html), and replace the suffix `/odata/v2/` with `/api-ext/` .

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
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
    
        Value of the `AuthnContextClassRef` tag, which is part of generated `OAuth2SAMLBearerAssertion` authentication.


    
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
    
        Add the *API Key* for the technical user that you copied in step 3 of this procedure.


    
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
    
5.  Select *New Property* on the right side of the *Destination Configuration* pane and add the following properties:


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
    
        Add the *API Key* for the technical user that you copied in step 3 of this procedure.


    
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
    
        **Value** of ***SuccessFactors Company ID***


    
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
    
        *nameQualifier*


    
    </td>
    <td valign="top">
    
        Security domain of the user, for which the access token is requested.


    
    </td>
    <td valign="top">
    
        **Value**:

    ***www.successfactors.com***


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *SystemUser*


    
    </td>
    <td valign="top">
    
        The name of the technical user, which would be used for executing a delta pull.


    
    </td>
    <td valign="top">
    
        **Value**:

    ***TECHNICAL\_USER\_INBOX\_CEF979F3***


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        *tc.clientId*


    
    </td>
    <td valign="top">
    
        This property is used to enable task updates to be pushed from SAP SuccessFactors.

    The value of this property is the value of the *uaa* \> *clientid* from the service key of the new service instance \(see *Step 1*\).

    > ### Note:  
    > Set this property only when you have enabled task updates to be pushed from SAP SuccessFactors \(see *Step 2*\). If you haven't completed this step, you might not be able to receive tasks from SAP SuccessFactors.


    
    </td>
    <td valign="top">
    
        **Value** of *clientid*


    
    </td>
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
    > Any value other than ***true*** \(for example ***false***\) would have the following effects:
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

    ***true***


    
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

    ***SuccessFactors***


    
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

    ***SAP SuccessFactors***


    
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

    ***SAP SuccessFactors Task***

    **Example for *tc.ui.label.de-DE***:

    ***SAP SuccessFactors Aufgabe***


    
    </td>
    </tr>
    </table>
    
6.  Select the *Use default JDK truststore* checkbox.

7.  Choose *Save*.

8.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP SuccessFactors, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP SuccessFactors.


