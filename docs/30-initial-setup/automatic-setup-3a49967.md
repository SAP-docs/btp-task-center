<!-- loio3a499676e7ae4282af84092f778e3737 -->

# Automatic Setup

Get started with the SAP Task Center service using a booster and creating a Task Center tile in your central point of entry for accessing apps.



<a name="loio3a499676e7ae4282af84092f778e3737__prereq_j2b_42y_j4b"/>

## Prerequisites

Before you continue with the automatic setup, make sure you meet all prerequisites in [Initial Setup](initial-setup-8347694.md).



## Procedure

1.  Access your global account page in the SAP BTP cockpit, and choose *Boosters* from the navigation menu.

2.  Search for *SAP Task Center* and start one of the following boosters, depening on the central point of entry for accessing apps, that you have set up in the prerequisites in [Initial Setup](initial-setup-8347694.md):

    **SAP Task Center Boosters**


    <table>
    <tr>
    <th valign="top">

    Your Central Point of Entry for Accessing Apps
    
    </th>
    <th valign="top">

    Name of the Booster
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, standard edition \(formerly known as SAP Launchpad service\)
    
    </td>
    <td valign="top">
    
    *Set up an account for SAP Task Center with SAP Build Work Zone, standard edition*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Build Work Zone, advanced edition
    
    </td>
    <td valign="top">
    
    *Set up an account for SAP Task Center with SAP Build Work Zone*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP SuccessFactors Work Zone
    
    </td>
    <td valign="top">
    
    *Set up an account for SAP Task Center with SAP SuccessFactors Work Zone*
    
    </td>
    </tr>
    </table>
    
    Follow the wizard to select your subaccount, organization, and space for the initial setup.

    > ### Note:  
    > The SAP Build Work Zone, standard edition Standard plan is set as default, but you can also use the Free plan instead. For more information about the Free plan of SAP Build Work Zone, standard edition, see [Using an Account with a Free Service Plan](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/1868e0dd101a4aa78b75e49ab46c992a.html).

3.  Create a Task Center tile as described in [Create a Task Center Tile](create-a-task-center-tile-70e7f6e.md).




<a name="loio3a499676e7ae4282af84092f778e3737__result_mfw_42y_j4b"/>

## Results

When the booster has finished, you can configure connectivity between SAP Task Center and the required SAP solutions in your subaccount.

The automatic setup does the following for you:

-   Enables Cloud Foundry.
-   Configures the entitlement of SAP Task Center.
-   Creates a default space, if you don't already have one.
-   Creates a *default\_taskcenter* service instance in *Services* \> *Instances and Subscriptions* \> *Instances* tab.
-   Creates a `service key` of the *default\_taskcenter* service instance.
-   Creates a subscription to the chosen central point of entry for accessing apps.
-   Assigns the required roles and role collections to the current user.
-   Creates a destination for integration of the chosen central point of entry for accessing apps with the SAP Task Center Web app.
-   Creates sample destinations for the SAP solution's connectivity with sample values for the properties. To configure connectivity between SAP Task Center and the required SAP solutions, you should clone the sample destinations and update the created sample properties in the cloned destination with valid destination property values.

    > ### Note:  
    > When using the cloned sample destinations, you must manually add the `tc.enabled` property. Without this property, the destination cannot be used by SAP Task Center.

    **Created Sample Destinations**


    <table>
    <tr>
    <th valign="top">

    Sample Destination
    
    </th>
    <th valign="top">

    Details
    
    </th>
    <th valign="top">

    More Information
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Alert\_Notification\_Connectivity\_ANS*
    
    </td>
    <td valign="top">
    
    Use this destination to set up notifications for end users.

    This destination is created only by the SAP Build Work Zone, standard edition booster.
    
    </td>
    <td valign="top">
    
    [Alert Notifications Connectivity](../40-administration/alert-notifications-connectivity-f6c9f3b.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Ariba*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Ariba.
    
    </td>
    <td valign="top">
    
    [Connect SAP Ariba and SAP Task Center](../40-administration/connect-sap-ariba-and-sap-task-center-d26b525.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *C4C*
    
    </td>
    <td valign="top">
    
    Use this destination for SAP Cloud for Customer and create a primary destination with the technical user.
    
    </td>
    <td valign="top" rowspan="2">
    
    [Connect SAP Cloud for Customer and SAP Task Center](../40-administration/connect-sap-cloud-for-customer-and-sap-task-center-ec09002.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *C4C\_PP*
    
    </td>
    <td valign="top">
    
    Use this destination for SAP Cloud for Customer and create a secondary destination for the principal propagation.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Concur\_exp*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Concur Expense.
    
    </td>
    <td valign="top" rowspan="2">
    
    [Connect SAP Concur and SAP Task Center](../40-administration/connect-sap-concur-and-sap-task-center-f354ef9.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Concur\_req*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Concur Request.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Fieldglass*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Fieldglass.
    
    </td>
    <td valign="top">
    
    [Connect SAP Fieldglass and SAP Task Center](../40-administration/connect-sap-fieldglass-and-sap-task-center-9367f0d.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Identity\_Authentication\_Connectivity\_IDS*
    
    </td>
    <td valign="top">
    
    This is a mandatory destination, that enables the functionalities related to user details within SAP Task Center.
    
    </td>
    <td valign="top">
    
    [Identity Directory Connectivity](../40-administration/identity-directory-connectivity-3dcfba9.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *S4HANA*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP S/4HANA.
    
    </td>
    <td valign="top">
    
    [Connect SAP S/4HANA and SAP Task Center](../40-administration/connect-sap-s-4hana-and-sap-task-center-143af9b.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *S4HANACloud*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP S/4HANA Cloud, public edition.
    
    </td>
    <td valign="top">
    
    [Connect SAP S/4HANA Cloud, public edition and SAP Task Center](../40-administration/connect-sap-s-4hana-cloud-public-edition-and-sap-task-center-0aff1b4.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *S4HANACloudPE*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP S/4HANA Cloud, private edition.
    
    </td>
    <td valign="top">
    
    [Connect SAP S/4HANA Cloud, private edition and SAP Task Center](../40-administration/connect-sap-s-4hana-cloud-private-edition-and-sap-task-center-50ce133.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAPBuildPA*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Build Process Automation from a local subaccount.
    
    </td>
    <td valign="top" rowspan="2">
    
    [Connect SAP Build Process Automation and SAP Task Center](../40-administration/connect-sap-build-process-automation-and-sap-task-center-e1e1dce.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAPBuildPA\_rem*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Build Process Automation from a remote subaccount.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SMC*
    
    </td>
    <td valign="top">
    
    Use this destination for the connection with SAP Marketing Cloud
    
    </td>
    <td valign="top">
    
    [Connect SAP Marketing Cloud and SAP Task Center](../40-administration/connect-sap-marketing-cloud-and-sap-task-center-18b3848.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Success\_Factors*
    
    </td>
    <td valign="top">
    
    Use this destination for SAP SuccessFactors and create a primary destination with the technical user.
    
    </td>
    <td valign="top" rowspan="2">
    
    [Connect SAP SuccessFactors and SAP Task Center](../40-administration/connect-sap-successfactors-and-sap-task-center-eae23f3.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Success\_Factors\_PP*
    
    </td>
    <td valign="top">
    
    Use this destination for SAP SuccessFactors and create a secondary destination for the principal propagation.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Task\_Center*
    
    </td>
    <td valign="top">
    
    This destination is created for the integration with your central point of entry for accessing apps.
    
    </td>
    <td valign="top">
    
    Do not change the settings of this destination.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Task\_Center\_global\_settings*
    
    </td>
    <td valign="top">
    
    This destination contains the global settings, valid for all destinations.
    
    </td>
    <td valign="top">
    
    [SAP Task Center Global Settings](../40-administration/sap-task-center-global-settings-99e5302.md)
    
    </td>
    </tr>
    </table>
    

**Related Information**  


[Boosters](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/fb1b56148f834749a2bf51127421610b.html)

[Create a Task Center Tile](create-a-task-center-tile-70e7f6e.md "Create a Task Center tile by folloing the links below.")

[Destinations](../40-administration/destinations-3470733.md "The SAP Task Center communicates with the task provider applications via predefined destinations in a customer subaccount.")

