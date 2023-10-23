<!-- loiobb3728b6073c4425b6cadc7b9c7b6b1b -->

# Creating the Primary Destination with the Technical User

You can set up the primary destination for SAP Cloud for Customer with the technical user either by using basic authentication, or via certificate.



Choose one of the options to see the procedure.

> ### Note:  
> Do not configure more than one primary destination to the same SAP Cloud for Customer system for each SAP Task Center. This will result in having duplicate tasks for end users.

![](images/IDS_2_a318d1a.png)



### Using Basic Authentication

**Prerequisites**

-   You have completed the steps in [Using Basic Authentication](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/16e287e9d7714b24a84381f968538a35.html) and have a *User ID* and *Password*.

-   You have your SAP Cloud for Customer tenant *URL*.


**Procedure**

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area.

2.  If you have run the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), then you already have a sample destination called *C4C*. You can use the sample destination or clone it, and update the properties as described next.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described next.

    Configure the properties of the destination as described in the following table:


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
    > -   The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.
    > 
    > -   If you change the *name* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.
    > 
    > -   If you change this destination name, you should also update the destination name for the principal propagation.


    
    </td>
    <td valign="top">
    
    **Example**:

    `C4C`


    
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
    
    Add the *URL* value from the *Prerequisites*.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://example.sapbydesign.com`


    
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
    
    Choose the *BasicAuthentication* option from the dropdown menu.


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*


    
    </td>
    <td valign="top">
    
    Add the *User* from *Prerequisites*.


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*


    
    </td>
    <td valign="top">
    
    Add the *Password* from *Prerequisites*.


    
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
    
    *tc.enabled*


    
    </td>
    <td valign="top">
    
    Enables SAP Task Center to connect to the configured task provider destination.

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
    
    Type of the task provider. This property is needed if you want to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md). 


    
    </td>
    <td valign="top">
    
    **Value**:

    `C4C`


    
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
    
    **Example**:

    `SAP Cloud for Customer`


    
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

    `SAP Cloud for Customer Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Cloud for Customer Aufgabe`


    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.

6.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP Cloud for Customer, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Cloud for Customer.




### Using Certificates

**Prerequisites**

-   You need the following for the setup of the destination:

    -   You have your SAP Cloud for Customer tenant *URL*.

    -   A certificate and its password

        For the connection to SAP Cloud for Customer using a certificate, you must have a *.p12* certificate and its password. You can use an already generated certificate \(see [Extract Public Certificate and Certificate Authority Chain](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/90c53693668f4958840f2ca619aed479.html#extract-public-certificate-and-certificate-authority-chain)\), or generate a new one by following the steps in [Use Destination Certificates](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/df1bb55a526942b9bee78fea2ebb3162.html?version=Cloud).



**Procedure**

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

2.  If you have run the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), then you already have a sample destination called *C4C*. You can use the sample destination or clone it, and update the properties as described below.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to Create a new destination and manually add the properties as described below.

    Configure the properties of the destination as described in the following table:


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
    > -   The name of the destination must not be longer than 16 characters, otherwise the status of the respective SAP Task Center connector will be set to `Error`.
    > 
    > -   If you change the *name* of an already configured destination, for which there are stored tasks in the `Task Cache`, the tasks in it will be repopulated.
    > 
    > -   If you change this destination name, you should also update the destination name for the principal propagation.


    
    </td>
    <td valign="top">
    
    **Example**:

    `C4C`


    
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
    
    Add the *URL* value from the *Prerequisites*.

    > ### Note:  
    > If you change the *URL* of an already configured destination, for which there are stored tasks in the task cache, the tasks in it will be repopulated.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://example.sapbydesign.com`


    
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
    
    Choose the *ClientCertificateAuthentication* option from the dropdown menu.


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Store Location*


    
    </td>
    <td valign="top">
    
    From the dropdown menu choose the certificate you downloaded in *Prerequisites*.


    
    </td>
    <td valign="top">
    
    **Example**:

    `c4c.p12`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Store Password*


    
    </td>
    <td valign="top">
    
    Add the certificate password from *Prerequisites*.


    
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
    
    *tc.enabled*


    
    </td>
    <td valign="top">
    
    Enables SAP Task Center to connect to the configured task provider destination.

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
    
    Type of the task provider. This property is needed if you want to configure a *Filter Tab* in the SAP Task Center Web app. Based on the value provided, the SAP Task Center Web app shows a predefined icon for the related *Filter Tabs*. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md). 


    
    </td>
    <td valign="top">
    
    **Value**:

    `C4C`


    
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
    
    **Example**:

    `SAP Cloud for Customer`


    
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

    `SAP Cloud for Customer Task`

    **Example for *tc.ui.label.de-DE***:

    `SAP Cloud for Customer Aufgabe`


    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.

6.  \(Optional\) To check the connectivity between the SAP Task Center service and SAP Cloud for Customer, use the monitoring functionality of SAP Task Center. For more information, see [Monitoring](monitoring-9b30be7.md).

    If you choose *Check Connection* in the destination configuration, you may not receive correct information about the connectivity between the SAP Task Center service and SAP Cloud for Customer.

7.  Continue with the steps described in [Using Client Certificate Authentication](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/a13a0773bce549bca5ff9358d8d21030/90c53693668f4958840f2ca619aed479.html).


