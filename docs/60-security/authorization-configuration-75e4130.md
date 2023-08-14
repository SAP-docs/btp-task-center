<!-- loio75e41301c2904561ae9bd1f93917540e -->

# Authorization Configuration

Assign roles to specific users using the SAP Task Center instance.

Authorizations are cumulative: If any one authorization allows access, access is granted.

SAP Business Technology Platform \(SAP BTP\) includes predefined platform roles that support the typical tasks performed by users when interacting with the platform. In addition, subaccount administrators can combine various scopes into a custom platform role that addresses their individual requirements. Certain activities, such as deployment of applications and assignment of roles to users or groups, require platform roles. These roles are assigned in the SAP BTP cockpit.



## Roles for Accessing the SAP Task Center API


<table>
<tr>
<th valign="top">

Role



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`TaskCenterAdmin` 



</td>
<td valign="top">

Permission to execute calls to the `Connector Status` API and monitor configured destinations and running background jobs.



</td>
</tr>
<tr>
<td valign="top">

`TaskCenterTenantOperator` 



</td>
<td valign="top">

Permission to export all data stored in the SAP Task Center cache, which is related to tasks and task users as a `.zip` file.



</td>
</tr>
</table>

**Related Information**  


[Assign Roles to Your Users](assign-roles-to-your-users-7e081d8.md "To assign roles to users, you need to add roles to one or more role collections and then assign these role collections to your users.")

[Assign Users to Role Collections](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/c5766765bda74ad59fe656977c8fa4d6.html?version=Cloud)

