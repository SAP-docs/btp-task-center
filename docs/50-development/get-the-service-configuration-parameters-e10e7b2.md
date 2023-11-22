<!-- loioe10e7b2b21ef49cd84e242089b789078 -->

# Get the Service Configuration Parameters

In the Cloud Foundry environment, you often require basic configuration parameters of the SAP Task Center to access the Task Center API.



<a name="loioe10e7b2b21ef49cd84e242089b789078__prereq_iz4_hfb_ffb"/>

## Prerequisites

You have the *Space Developer* role assigned to your subaccount.



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, select *Services* \> *Instances and Subscriptions* in the navigation area, and go to *Instances*.

2.  Choose the row of the *SAP Task Center* service to see the details of this instance.

3.  In the *Service Keys* section choose the available service key, or create one, if no service instance is available.

4.  In the *Credentials* pop-up, open the *JSON* format and search for the parameters listed in the table:


    <table>
    <tr>
    <th valign="top">

    Parameter Name
    
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
    
    <code><i>endpoints</i> &gt; <i>inbox_rest_url</i></code> 
    
    </td>
    <td valign="top">
    
    Base URL of the SAP Task Center 
    
    </td>
    <td valign="top">
    
    For SAP Task Center Web app use `https://api.one-inbox-sap.cfapps.sap.hana.ondemand.com/inbox-service/` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <code><i>uaa</i> &gt; <i>clientid</i></code> 
    
    </td>
    <td valign="top">
    
    Client ID for OAuth2
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <code><i>uaa</i> &gt; <i>clientsecret</i></code> 
    
    </td>
    <td valign="top">
    
    Client secret for OAuth2
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <code><i>uaa</i> &gt; <i>url</i></code> 
    
    </td>
    <td valign="top">
    
    Authentication base URL for OAuth2 or SAML
    
    </td>
    <td valign="top">
    
    `https://<subdomain>.authentication.<region host>.hana.ondemand.com` 
    
    </td>
    </tr>
    </table>
    

