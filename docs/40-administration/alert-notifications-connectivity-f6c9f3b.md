<!-- loiof6c9f3b7e57942d6b5f5a7ac1f1af82d -->

# Alert Notifications Connectivity

Configure the *Alert\_Notification\_Connectivity\_ANS* destination, as part of the enablement of notifications for end users in the SAP Task Center Web app.



<a name="loiof6c9f3b7e57942d6b5f5a7ac1f1af82d__prereq_e2b_w4w_tyb"/>

## Prerequisites

-   You have completed the settings in SAP Build Work Zone, standard edition, as described in [Enable Notifications for End Users](enable-notifications-for-end-users-caf2543.md), and have the values of the following properties:

    -   *Host*
    -   *OAuth 2.0 Client ID*
    -   *Client Secret*
    -   *Token Endpoint*




## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> ***Destinations* tab from the navigation area on the left.

2.  Create a new destination and manually add the properties as described below.

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
    
    Add `Alert_Notification_Connectivity_ANS` as name of this destination.


    
    </td>
    <td valign="top">
    
    **Value**:

    `Alert_Notification_Connectivity_ANS`


    
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

    `Notification Destination`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*


    
    </td>
    <td valign="top">
    
    Add the value of the *Host* property from the *Prerequisites* section and add `https://` before the *Host* value.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://notifications.cfapps.yourdatacenter.hana.ondemand.com`


    
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
    
    Choose the *OAuth2ClientCredentials* option from the dropdown menu.


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client ID*


    
    </td>
    <td valign="top">
    
    Add the value of the *OAuth 2.0 Client ID* property from the *Prerequisites* section.


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*


    
    </td>
    <td valign="top">
    
    Add the value of the *Client Secret* property from the *Prerequisites* section.


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*


    
    </td>
    <td valign="top">
    
    Add the value of the *Token Endpoint* property from the *Prerequisites* section and add `https://` before the *Token Endpoint* value.


    
    </td>
    <td valign="top">
    
    **Example**:

    `https://example-notifications.authentication.yourdatacenter.hana.ondemand.com/oauth/token`


    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.


**Related Information**  


[Enable Notifications for End Users](enable-notifications-for-end-users-caf2543.md "Enable notifications for end users, ensuring that they receive timely task alerts.")

