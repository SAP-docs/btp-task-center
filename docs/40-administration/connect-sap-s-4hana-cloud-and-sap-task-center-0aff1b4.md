<!-- loio0aff1b46b5574ea0b3e32f25fc551799 -->

# Connect SAP S/4HANA Cloud and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP S/4HANA Cloud on SAP BTP, Cloud Foundry environment.



**Context**

![](images/PushWithMTLS_ad82bb2.png)



### Connect SAP S/4HANA Cloud and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP S/4HANA Cloud on SAP BTP, Cloud Foundry environment.

**Prerequisites**

1.  You have completed all prerequisites listed in [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).

2.  Create a dedicated service instance for SAP Task Center in the Cloud Foundry subaccount, where your initial SAP Task Center instance was created. This enables task updates to be pushed from your ABAP system. Follow the steps in [Create a Service Instance Using the SAP BTP Cockpit](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/dc9af9fd363b4e989af6ff2f19548d32.html?version=Cloud) and create a service key for the service instance. Open the JSON file of the service key and get the following values:

    -   *endpoints* \> *inbox\_rest\_url*
    -   *uaa* \> *url*
    -   *uaa* \> *clientid*
    -   *uaa* \> *clientsecret*

3.  You have performed the steps in [Integrating SAP Task Center](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/0fdb31ce0dff4537a1ac6f98d4d34dbd.html). To complete the setup of this destination, you need the following parameters from [Create a Communication Arrangement](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/913ff1a47a6447e3b7bee17fa6f275ff.html):

    -   *Service URL/Service Interface* that you can find when creating a communication arrangement.

    -   *SAML2 Audience*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *Client ID*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *Token Service URL*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *User Name*, that you have created for the technical communication user.
    -   *Password*, that you have created for the technical communication user.


> ### Note:  
> Do not configure more than one destination to the same SAP S/4HANA Cloud system for one SAP Task Center. This will result in having duplicate tasks for end users.

**Procedure**

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area on the left.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *S4HANACloud*. You can use the sample destination or clone it, and update the properties as described below.

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
    > The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to ***Error***.


    
    </td>
    <td valign="top">

    **Example**:

    ***S4HANACloud***


    
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

    ***SAP S/4HANA Cloud Connector***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *URL*


    
    </td>
    <td valign="top">

    Add the *Service URL/Service Interface* value, and remove `sap/opu/odata4/sap/api_task_spi_replication/default/sap/api_task_spi_replication/0001/?sap-client=100`

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">

    **Example**:

    ***https://example-api.s4hana.ondemand.com/***


    
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

    ***https://example.s4hana.ondemand.com***


    
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

    ***urn:oasis:names:tc:SAML:2.0:ac:classes:X509***


    
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

    ***COM501SID100***


    
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

    ***https://example-api.s4hana.ondemand.com/sap/bc/sec/oauth2/token***


    
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

    ***COM501SID100***


    
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

    *tc.clientId*


    
    </td>
    <td valign="top">

    This property is used to enable task updates to be pushed from SAP S/4HANA Cloud.

    The value of this property is the value of the *uaa* \> *clientid* from the service key of the new service instance \(see [Create a Communication Arrangement](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/913ff1a47a6447e3b7bee17fa6f275ff.html?version=latest)\).

    > ### Note:  
    > Set this property only when you have completed the SAP Task Center integration from the *Prerequisites* section. If you haven't completed this step, you might not be able to receive tasks from SAP S/4HANA Cloud.


    
    </td>
    <td valign="top">

    **Value** of *clientid*


    
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

    ***S/4HANACloud***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *tc.ui.group*

    and

    *:tc.ui.group.\[language\_code\]*


    
    </td>
    <td valign="top">

    \(Optional\) Provides grouping for the SAP Task Center Web app *Filter Tabs*.

    You can define a separate property for a filter tab translation for each of the supported languages \(see [Supported Languages](../10-what-is/supported-languages-c66c693.md)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.group*You can define a separate property with the value You can define a separate property for a task label translation for each of the supported languages \(see ***property for a task label translation for each of<default\_translation\>*** for a default translation of the group name.

    -   the *tc.ui.group.de-DE* property with the value ***<German\_translation\>*** for a German translation of the group name.


    For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md).


    
    </td>
    <td valign="top">

    ***SAP S/4HANA Cloud***


    
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

    [Supported Languages](../10-what-is/supported-languages-c66c693.md)\), by appending the respective language code to the property.

    For example, add:

    -   the *tc.ui.label* property with the value ***<default\_translation\>*** for a default translation of the label.

    -   the *tc.ui.label.de-DE* property with the value ***<German\_translation\>*** for a German translation of the label.


    For more information, see [Configure Labels in SAP Task Center Web App](configure-labels-in-sap-task-center-web-app-a0be9ad.md).


    
    </td>
    <td valign="top">

    **Example for *tc.ui.label***:

    ***SAP S/4HANA Cloud Task***

    **Example for *tc.ui.label.de-DE***:

    ***SAP S/4HANA Cloud Aufgabe***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *URL.queries.sap-client*


    
    </td>
    <td valign="top">

    The client number of the SAP S/4HANA Cloud system.


    
    </td>
    <td valign="top">

    **Example**:

    ***100***


    
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
    
4.  Save your configuration.

5.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP S/4HANA Cloud, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP S/4HANA Cloud.




### Connect SAP S/4HANA Cloud and SAP Task Center Using mTLS

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP S/4HANA Cloud on SAP BTP, Cloud Foundry environment.

**Prerequisites**

1.  You have completed all prerequisites listed in [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).

2.  Create a dedicated service instance for SAP Task Center in the Cloud Foundry subaccount, where your initial SAP Task Center instance was created. This enables task updates to be pushed from your ABAP system. Follow the steps in [Create a Service Instance Using the SAP BTP Cockpit](../30-initial-setup/create-a-service-instance-using-the-sap-btp-cockpit-dc9af9f.md) and create a service key with certificate for the new service instance. Open the JSON file of the service key and get the following values:

    -   *endpoints* \> *inbox\_rest\_url*
    -   *uaa* \> *url*
    -   *uaa* \> *clientid*
    -   *uaa* \> *certificate*
    -   *uaa* \> *certurl*
    -   *uaa* \> *key*

3.  Use the values of *uaa* \> *certificate* and *uaa* \> *key* to create the ***outbound.p12*** certificate, which is used for the outbound communication from SAP S/4HANA Cloud to SAP Task Center.

    1.  Copy the value of the *uaa* \> *certificate* parameter \(without the quotation marks\) to a new text file.

    2.  Copy the value of the *uaa* \> *key* parameter \(without the quotation marks\) and append it to text file from the previous step.

    3.  Make sure you replace all appearances of *\\n* with line feeds.

        The final version of the certificate should have the following structure:

        > ### Example:  
        > \-----BEGIN CERTIFICATE-----
        > 
        > ...
        > 
        > \-----END CERTIFICATE-----
        > 
        > \-----BEGIN CERTIFICATE-----
        > 
        > ...
        > 
        > \-----END CERTIFICATE-----
        > 
        > \-----BEGIN CERTIFICATE-----
        > 
        > ...
        > 
        > \-----END CERTIFICATE-----
        > 
        > \-----BEGIN RSA PRIVATE KEY-----
        > 
        > ...
        > 
        > \-----END RSA PRIVATE KEY-----

    4.  Save the text file as ***outbound.p12***.


4.  Create the ***inbound.p12*** certificate, which is used for the inbound communication from SAP Task Center to SAP S/4HANA Cloud.

    For the connection to SAP S/4HANA Cloud, using mTLS, you must have a *.p12* certificate and its password. You can use an already generated certificate, or generate a new one by following the steps in [Use Destination Certificates](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/df1bb55a526942b9bee78fea2ebb3162.html). You can download the certificate by using the Destination service REST API. For more information, see [Destination Service REST API](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/23ccafbea18f4b65919a2799f2cd20e6.html).

    We'll further refer to this certificate as the inbound communication certificate ***inbound.p12***.

5.  Log on to your Cloud Foundry subaccount, select the **Destinations** tab from the navigation area on the left, and chose **Download Trust**.

6.  Perform the steps in [Integrating SAP Task Center](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/0fdb31ce0dff4537a1ac6f98d4d34dbd.html).

    You'll need the ***inbound.p12*** and ***outbound.p12*** certificates from the previous steps when setting up *Users for Inbound Communication* and *Users for Outbound Communication* in the communication system.

    Once you have enabled the communication between your ABAP system and SAP Task Center, make sure you have the following parameters from [Create a Communication Arrangement Using mTLS](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/107ee140b88f4c7ea04e741dc172bb22.html?version=latest):

    -   *Service URL/Service Interface* that you can find when creating a communication arrangement.

    -   *SAML2 Audience*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *Client ID*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.
    -   *Token Service URL*, that you can find in the *OAuth2.0 Details* when creating the communication arrangement.


> ### Note:  
> Do not configure more than one destination to the same SAP S/4HANA Cloud system for one SAP Task Center. This will result in having duplicate tasks for end users.

**Procedure**

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area on the left.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you already have a sample destination called *S4HANACloud*. You can use the sample destination or clone it, and update the properties as described below.

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
    > The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to ***Error***.


    
    </td>
    <td valign="top">

    **Example**:

    ***S4HANACloud***


    
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

    ***SAP S/4HANA Cloud Connector***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *URL*


    
    </td>
    <td valign="top">

    Add the *Service URL/Service Interface* value, and remove `sap/opu/odata4/sap/api_task_spi_replication/default/sap/api_task_spi_replication/0001/?sap-client=100`

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">

    **Example**:

    ***https://example-api.s4hana.ondemand.com/***


    
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

    ***https://example.s4hana.ondemand.com***


    
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

    ***urn:oasis:names:tc:SAML:2.0:ac:classes:X509***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Use mTLS for token retrieval*


    
    </td>
    <td valign="top">

    Make sure this checkbox is selected.


    
    </td>
    <td valign="top">

     


    
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

    ***COM501SID100***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Token Service Key Store Location*


    
    </td>
    <td valign="top">

    Choose the *inbound.p12* certificate you have downloaded in the *Prerequisites* section.


    
    </td>
    <td valign="top">

     


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Token Service Key Store Password*


    
    </td>
    <td valign="top">

    Add the password to the inbound communication certificate ***inbound.p12*** from the *Prerequisites* section.


    
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

    Add the *Token Service URL*, that you copied in the *Prerequisites* section.


    
    </td>
    <td valign="top">

    **Example**:

    ***https://example-api.s4hana.ondemand.com/sap/bc/sec/oauth2/token***


    
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
    > Any value other than ***true*** \(for example ***false***\) would have the following effects:
    > 
    > -   The previously stored tasks are kept in the `Task Cache`.
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

    Type of the task provider.


    
    </td>
    <td valign="top">

    **Value**:

    ***S/4HANACloud***


    
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

    ***SAP S/4HANA Cloud***


    
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

    ***SAP S/4HANA Cloud Task***

    **Example for *tc.ui.label.de-DE***:

    ***SAP S/4HANA Cloud Aufgabe***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *URL.queries.sap-client*


    
    </td>
    <td valign="top">

    The client number of the SAP S/4HANA Cloud system.


    
    </td>
    <td valign="top">

    **Example**:

    ***100***


    
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
    
4.  Save your configuration.

5.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP S/4HANA Cloud, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

6.  If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP S/4HANA Cloud.


