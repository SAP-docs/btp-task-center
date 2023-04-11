<!-- loio3dcfba91f69942b29bd924f75bf51c10 -->

# Identity Directory Connectivity

Configure the *Identity\_Authentication\_Connectivity\_IDS* destination to connect to the identity directory of Identity Authentication and retrieve the required information about the end users.



**Context**

Create this destination to enable the communication between SAP Task Center and the identity directory. This is a mandatory destination that enhances the SAP Task Center functionality by adding user information, and the option to search for users in the Web app.

> ### Note:  
> The user information, coming from Identity Authentication, is stored in the SAP Task Center cache. Updates of the user information in Identity Authentication might take up to 24 hours to be visualized in the SAP Task Center Web app.

You can set up this connectivity either by using the basic authentication, or via certificate. Choose one of the options to see the procedure:

![](images/IDS_2_a318d1a.png)



### Using Basic Authentication

**Prerequisites**

-   You have the tenant ID of your Identity Authentication and have created the URL, following the pattern:

    `https://<tenant ID>.accounts.ondemand.com/scim`

    > ### Tip:  
    > The *Tenant ID* is an automatically generated ID by the system. The first administrator created for the tenant receives an activation e-mail with a URL in it. This URL contains the *tenant ID*. For more information about your tenants, see [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/f56e6f24e373404087d6a1a9a13515a2.html).

-   You have created a system as administrator in Identity Authentication and have the user ID and password of this system.

    For more information, see [Add System as Administrator](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/bbbdbdd3899942ce874f3aae9ba9e21d.html#loiocefb742a36754b18bbe5c3503ac6d87c).


 **Procedure** 

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area on the left.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you have an already created destination with the name *Identity\_Authentication\_Connectivity\_IDS*. Configure the properties as described below.

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

    Add ***Identity\_Authentication\_Connectivity\_IDS*** as name of this destination.


    
    </td>
    <td valign="top">

    **Value**:

    ***Identity\_Authentication\_Connectivity\_IDS***


    
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

    ***Identity Authentication Connectivity***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *URL*


    
    </td>
    <td valign="top">

    Add the URL you created in *Prerequisites*.


    
    </td>
    <td valign="top">

    **Example**:

    ***https://example.accounts.ondemand.com/scim***


    
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

    Add the user ID of the system as administrator.

    For more information, see *Prerequisites*.


    
    </td>
    <td valign="top">

     


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Password*


    
    </td>
    <td valign="top">

    Add the password of the system as administrator.

    For more information, see *Prerequisites*.


    
    </td>
    <td valign="top">

     


    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.




### Using Certificates

**Prerequisites**

-   You have the tenant ID of your Identity Authentication and have created the URL, following the pattern:

    `https://<tenant ID>.accounts.ondemand.com/scim`

    > ### Tip:  
    > The *Tenant ID* is an automatically generated ID by the system. The first administrator created for the tenant receives an activation e-mail with a URL in it. This URL contains the *tenant ID*. For more information about your tenants, see [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/f56e6f24e373404087d6a1a9a13515a2.html).

-   In Identity Authentication you have:

    1.  Created a system as administrator and have the user ID and password of this system
    2.  Created and downloaded a certificate and have its password

    For more information, see [Add System as Administrator](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/bbbdbdd3899942ce874f3aae9ba9e21d.html#loiocefb742a36754b18bbe5c3503ac6d87c).

    > ### Note:  
    > Keep in mind, that the created certificate is generally valid for one year. You have to update this certificate before it expires, to continue retrieving the required information about the business users. In case you don't rotate the certificates, business users might have issues viewing user-related information in SAP Task Center \(for example the *Created By* field\).


 **Procedure** 

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area on the left.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you have an already created destination with the name *Identity\_Authentication\_Connectivity\_IDS*. Configure the properties as described below.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described below.

3.  In the *Destinations* editor upload the certificate you have from the *Prerequisites* section. For more information, see [Use Destination Certificates](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/df1bb55a526942b9bee78fea2ebb3162.html).

4.  Configure the properties of the destination as described in the following table:


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

    Add ***Identity\_Authentication\_Connectivity\_IDS*** as name of this destination.


    
    </td>
    <td valign="top">

    **Value**:

    ***Identity\_Authentication\_Connectivity\_IDS***


    
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

    ***Identity Authentication Connectivity***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *URL*


    
    </td>
    <td valign="top">

    Add the URL you created in *Prerequisites*.


    
    </td>
    <td valign="top">

    **Example**:

    ***https://example.accounts.ondemand.com/scim***


    
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

    *Use client provided certificate*


    
    </td>
    <td valign="top">

    Make sure this checkbox is deselected.


    
    </td>
    <td valign="top">

     


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Key Store Location*


    
    </td>
    <td valign="top">

    Choose the certificate you uploaded in *Step 3* from the dropdown menu.


    
    </td>
    <td valign="top">

    **Example**:

    ***ids.p12***


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Key Store Password*


    
    </td>
    <td valign="top">

    Add the password of the certificate.

    For more information, see *Prerequisites*.


    
    </td>
    <td valign="top">

     


    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*.


