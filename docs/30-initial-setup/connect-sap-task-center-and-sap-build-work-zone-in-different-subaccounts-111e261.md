<!-- loio111e261c0429406dbff15a4b85eecaf9 -->

# Connect SAP Task Center and SAP Build Work Zone in Different Subaccounts

Follow the steps in this topic to learn how to connect SAP Task Center with SAP Build Work Zone as a central point of entry for accessing applications, when both are in different subaccounts.



## Context

You can use one of the supported SAP Build Work Zone offerings as a central point of entry, even if your SAP Task Center and SAP Build Work Zone are in different subaccounts. You need to have two subaccounts in the same global account, and configure the integration between the two applications in SAP Cloud Identity Services - Identity Authentication.

For more information on the supported SAP Build Work Zone offerings, which can be set up as a central point of entry for accessing applications for SAP Task Center, see [Create a Task Center Tile](create-a-task-center-tile-70e7f6e.md) and [Verify Your Central Point of Entry for Accessing Applications](https://help.sap.com/docs/task-center/sap-task-center/834769400794464489f390350a82bbd6.html#loio834769400794464489f390350a82bbd6__EntryPoint).



## Prerequisites

You have one global account with two subaccounts. The first one has a subscription to SAP Task Center - this is your SAP Task Center subaccount. The second one has a subscription to the SAP Build Work Zone of your choice - this is your SAP Build Work Zone subaccount.

-   In the SAP Task Center subaccount you have:
    -   Entitlements to create a service instance of SAP Task Center. For more information, see [Check Your Entitlements and Commercial Model](https://help.sap.com/docs/task-center/sap-task-center/834769400794464489f390350a82bbd6.html?locale=en-US&state=PRODUCTION&version=Cloud#loio834769400794464489f390350a82bbd6__CommercialModel).

    -   Prepared your SAP Business Technology Platform \(SAP BTP\) account as described in [Prepare Your SAP Business Technology Platform \(SAP BTP\) Account](https://help.sap.com/docs/task-center/sap-task-center/initial-setup?version=Cloud#loio834769400794464489f390350a82bbd6__BTPaccount).

        As part of this, you have established trust of type OpenID Connect with the User Account and Authentication \(UAA\) of your SAP Task Center subaccount, using Identity Authentication. For more information, see [Establishing Trust of Type OpenID Connect](https://help.sap.com/docs/btp/sap-business-technology-platform/establishing-trust-automatically).

        For more information, see [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html) or [Manually Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/7c6aa87459764b179aeccadccd4f91f3.html).

    -   Set up the integration with SAP Cloud Identity Services and Identity Authentication as described in [Integrate with SAP Cloud Identity Services](https://help.sap.com/docs/task-center/sap-task-center/834769400794464489f390350a82bbd6.html?locale=en-US&state=PRODUCTION&version=Cloud#loio834769400794464489f390350a82bbd6__CIS).
    -   You have created a service instance of SAP Task Center and you have created a service key. For more information, see [Create a Service Instance Using the SAP BTP Cockpit](create-a-service-instance-using-the-sap-btp-cockpit-dc9af9f.md).

        From the service key you need the values of the parameters *html5-apps-repo*, *endpoints* and *uaa* \> *url*.

    -   You have a subscription to SAP Task Center. For more information on how to subscribe to SAP Task Center, see [Create a Subscription to the SAP Task Center Service](create-a-subscription-to-the-sap-task-center-service-fd137e3.md).

-   In the SAP Build Work Zone subaccount you have:
    -   Entitlements for the SAP Build Work Zone of your choice.
    -   Established trust of type OpenID Connect with the same identity provider as the one in the SAP Task Center subaccount. For more information, see [Establishing Trust of Type OpenID Connect](https://help.sap.com/docs/btp/sap-business-technology-platform/establishing-trust-automatically).

        For more information, see [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html) or [Manually Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/7c6aa87459764b179aeccadccd4f91f3.html).

    -   You have a subscription to the SAP Build Work Zone of your choice.




## Procedure

1.  In the administration console for SAP Cloud Identity Services, go to *Applications and Resources* \> *Applications*.

2.  Make sure that you see both applications of the SAP Task Center and SAP Build Work Zone subaccounts in the *Bundled Applications* section.

3.  Choose the SAP Build Work Zone subaccount in the *Bundled Application* section and configure a dependency to SAP Task Center as an application. For more information, see [Configure Integration Between Applications](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/communicate-between-applications).

4.  Note down the dependency name of the newly created dependency.
5.  In the SAP BTP cockpit, go to your SAP Build Work Zone subaccount and open *Connectivity* \> *Destinations*.
6.  Create a new destination with the following parameters:


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
    
    Add `TaskCenter`.
    
    </td>
    <td valign="top">
    
    **Value**:

    `TaskCenter`
    
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
    
    Add the value of *uaa* \> *url* from the *Prerequisites* section.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://sample.authentication.sap.hana.ondemand.com`
    
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
    
    Choose the *NoAuthentication* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
    Add the following additional properties:


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
    
    *html5-apps-repo*
    
    </td>
    <td valign="top">
    
    Add the value of the *html5-apps-repo* parameter from the service key of the SAP Task Center subaccount.
    
    </td>
    <td valign="top">
    
    **Example**:

    `{"app_host_id":"abcd1234-ab12-ab12-ab12-abcdef123456,abcd1234-ab12-ab12-ab12-abcded123456"}`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *endpoints*
    
    </td>
    <td valign="top">
    
    Add the value of the *endpoints* parameter from the service key of the SAP Task Center subaccount.
    
    </td>
    <td valign="top">
    
    **Example**:

    `{"inbox_odata_url":"https://api.sampleurl.sap.hana.ondemand.com/odata/v2", "inbox_rest_url":"https://api.sampleurl.sap.hana.ondemand.com/task-center-service"}"`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *sap.cloud.service*
    
    </td>
    <td valign="top">
    
    Add `com.sap.bpm.inbox-service`.
    
    </td>
    <td valign="top">
    
    **Value**:

    `com.sap.bpm.inbox-service`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *IASDependencyName*
    
    </td>
    <td valign="top">
    
    Add the dependency name of the newly created dependency \(see *Step 4* in this *Procedure*\).
    
    </td>
    <td valign="top">
    
    **Example**:

    `testsystem`
    
    </td>
    </tr>
    </table>
    



### Result

After setting up the destination, you have completed the integration between SAP Task Center and SAP Build Work Zone as a central point of entry for accessing applications.



### Next Steps

Set up the SAP Task Center tiles, as described in [Create a Task Center Tile](create-a-task-center-tile-70e7f6e.md) and [Create a Task Center Administration Tile](create-a-task-center-administration-tile-8053d72.md).

