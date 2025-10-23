<!-- loio7e081d89c4fa4926b3b0fe20a62c9fc6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Assign Roles to Your Users

To assign roles to users, you need to add roles to one or more role collections and then assign these role collections to your users.



## Prerequisites

In your subaccount, *Security* \> *Administrators* section, you have the *User & Role Administrator* role assigned to your user.



## Create Role Collections

1.  Navigate to your subaccount in the SAP BTP cockpit.
2.  In the navigation area, under *Security*, choose *Role Collections*.
3.  Choose *Create New Role Collection \(*<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>*\)*, enter a name and optionally a description. Then choose *Save*.
4.  Choose the new role collection, then choose *Edit*.
5.  Choose the *Role Name* field. In the new *Select: Role* window, in the *Application Identifier* field search for the entry that begins with *one-inbox-lservice*.
6.  Select a role depending on your authorization configuration requirements, choose *Add*, and save the role collection.
7.  Keep adding roles or create additional role collections according to your requirements.



## Assign Role Collections to Users

You can either choose to assign role collections in the SAP BTP cockpit or in SAP Cloud Identity Services - Identity Authentication.



### Assign Role Collections in the SAP BTP Cockpit 

1.  Navigate to your subaccount in the SAP BTP cockpit.
2.  In the navigation area, under *Security*, choose *Trust Configuration*.
3.  Select the name of your identity provider.
4.  Select *Role Collection Assignment*.
5.  Enter the user login name into the *User* input field, then choose *Show Assignments*.
6.  If the user is not added to the respective identity provider, add the user by selecting *Add User* in the confirmation dialog box.
7.  Choose *Assign Role Collection*, then select the desired role collection and choose *Assign Role Collection*.
8.  Keep editing the role assignments according to your requirements.



### Assign Role Collections in Identity Authentication 

**Prerequisites**

-   There must already be a role collection in SAP BTP cockpit that you want to assign to a user.

-   You must have administrator rights for Identity Authentication.


**Procedure**

1.  In your Identity Authentication, navigate to *Users & Authorizations*.
2.  Create a new group and name it similarly to the role collection name that you created in the SAP BTP cockpit. For more information on how to create a group, see [Create a Group](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/create-new-user-group).
3.  After creating the group, open it and add the users who should receive the SAP BTP role collection.
4.  Go to the SAP BTP cockpit and open *Trust Configuration*. Make sure you have established trust with the identity provider that SAP Task Center trusts and select the identity provider from the list.
5.  In the *User Groups* section of the selected identity provider, create a mapping between the role collection from the SAP BTP cockpit and the Identity Authentication group you created previously.

    For more information, see [Assign User Groups to Role Collections](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-user-groups-to-role-collections).


**Related Information**  


[Authorization Configuration](authorization-configuration-75e4130.md "Assign roles to specific users using the SAP Task Center instance.")

[Assign Users to Role Collections](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/c5766765bda74ad59fe656977c8fa4d6.html?version=Cloud)

[Map Role Collections to User Groups](https://help.sap.com/docs/btp/sap-business-technology-platform/map-role-collections-to-user-groups)

