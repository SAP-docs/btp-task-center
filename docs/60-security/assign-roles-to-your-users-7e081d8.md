<!-- loio7e081d89c4fa4926b3b0fe20a62c9fc6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Assign Roles to Your Users

To assign roles to users, you need to add roles to one or more role collections and then assign these role collections to your users.



<a name="loio7e081d89c4fa4926b3b0fe20a62c9fc6__prereq_ljr_cng_cfb"/>

## Prerequisites

In your subaccount, *Security* \> *Administrators* section, you have the *User & Role Administrator* role assigned to your user.

**Related Information**  


[Authorization Configuration](authorization-configuration-75e4130.md "Assign roles to specific users using the SAP Task Center instance.")

[Assign Users to Role Collections](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/c5766765bda74ad59fe656977c8fa4d6.html?version=Cloud)

 <a name="loio4e4af2f3c4d8479b93b111587a6a17b1"/>

<!-- loio4e4af2f3c4d8479b93b111587a6a17b1 -->

## Create Role Collections



## Procedure

1.  Navigate to your subaccount in the SAP BTP cockpit.

2.  In the navigation area, under *Security*, choose *Role Collections*.

3.  Choose *Create New Role Collection \(*<span style="color:#346187;"><span class="SAP-icons"></span></span>*\)*, enter a name and optionally a description. Then choose *Save*.

4.  Choose the new role collection, then choose *Edit*.

5.  Choose the *Role Name* field. In the new *Select: Role* window, in the *Application Identifier* field search for the entry that begins with *one-inbox-service*.

6.  Select a role depending on your authorization configuration requirements, choose *Add*, and save the role collection.

7.  Keep adding roles or create additional role collections according to your requirements.


 <a name="loio80d42d82cef047dc8ff3841f398edb36"/>

<!-- loio80d42d82cef047dc8ff3841f398edb36 -->

### Assign Role Collections to Users



## Procedure

1.  Navigate to your subaccount in the SAP BTP cockpit.

2.  In the navigation area, under *Security*, choose *Trust Configuration*.

3.  Select the name of your identity provider.

4.  Select *Role Collection Assignment*.

5.  Enter the user login name into the *User* input field, then choose *Show Assignments*.

6.  If the user is not added to the respective identity provider, add the user by selecting *Add User* in the confirmation dialog box.

7.  Choose *Assign Role Collection*, then select the desired role collection and choose *Assign Role Collection*.

8.  Keep editing the role assignments according to your requirements.


