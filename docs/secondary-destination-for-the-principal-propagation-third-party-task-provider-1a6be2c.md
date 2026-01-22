<!-- loio1a6be2ce9aae46729bc24d9fef98e250 -->

# Secondary Destination for the Principal Propagation \(Third-Party Task Provider\)

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from a third-party task provider.



<a name="loio1a6be2ce9aae46729bc24d9fef98e250__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have completed the prerequisites, descibed in [Connect a Third-Party Task Provider and SAP Task Center](connect-a-third-party-task-provider-and-sap-task-center-c6362b6.md).

-   You have performed the steps described in [Primary Destination with the Technical User \(Third-Party Task Provider\)](primary-destination-with-the-technical-user-third-party-task-provider-b55629f.md).


> ### Note:  
> Do not configure more than one destination to the same third-party task provider system for one SAP Task Center. This will result in having duplicate tasks for end users.



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> ***Destinations* tab from the navigation area.

2.  Create a new destination and manually add the properties as described in the following table.


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
    
    The destination name for the principal propagation must be the same as the name of the primary destination for the technical user, but with the `_PP` suffix added.

    For more information about the name of the primary destination, see [Primary Destination with the Technical User \(Third-Party Task Provider\)](primary-destination-with-the-technical-user-third-party-task-provider-b55629f.md).

    > ### Note:  
    > If you change the name of the primary destination, you should also update this destination name.


    
    </td>
    <td valign="top">
    
    **Example**:

    `MyThirdParty_PP`
    
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
    
    Use the third-party task provider tenant URL.

    Please, note that SAP Task Center appends additional attributes \(for example, `/task-provider/v2/`\) to this URL.
    
    </td>
    <td valign="top">
    
    **Example**:

    `https://sample_task_provider.com`
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Make sure that you maintain properties such as *Authentication*, so that a valid security token is returned by the destination. This token will be used in the end-user flows, for instance, retrieving task details, or perform actions.

    For more information about the authentication methods, see [HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/http-destinations?version=Cloud).

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
    
    *tc.provider\_type*
    
    </td>
    <td valign="top">
    
    Type of the task provider.
    
    </td>
    <td valign="top">
    
    **Value**:

    `Custom`
    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Choose *Save*.


