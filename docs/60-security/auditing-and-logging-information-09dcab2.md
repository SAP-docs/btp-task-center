<!-- loio09dcab2209014904a2e2dc85830f7e3e -->

# Auditing and Logging Information

Here you can find a list of the security events that are logged by the SAP Task Center service.

**Security Events Written in Audit Logs**


<table>
<tr>
<th valign="top">

Event Grouping



</th>
<th valign="top">

What Events Аre Logged



</th>
<th valign="top">

How to Identify Related Log Events



</th>
</tr>
<tr>
<td valign="top" rowspan="7">

Tenant events



</td>
<td valign="top">

Create new tenant

Action: `about-to-create-account-data`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message: *Creation of data for <account\> started by <user\>*



</td>
</tr>
<tr>
<td valign="top">

Create new tenant

Action: `create-account-data-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message: *Creation of data for <account\> completed*



</td>
</tr>
<tr>
<td valign="top">

Create new tenant

Action: `create-account-data-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message: *Creation of data for <account\> failed. Reason for failing the creation is <Reason\>*



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `requested-to-delete-account-data`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion \(reason: <reason\>\) of data for <account\> requested by <user\>*



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `about-to-delete-account-data`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion \(reason: <reason\>\) of data for <account\> started by <user\>*



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `delete-account-data-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion \(reason: <reason\>\) of data for <account\> completed*



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `delete-account-data-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion \(reason: <reason\>\) of data for <account\> failed. Reason for failing the deletion is <Reason\>*



</td>
</tr>
<tr>
<td valign="top" rowspan="10">

Instance events



</td>
<td valign="top">

Create a new service instance

Action: `about-to-create-service-instance`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message: *Creation of service instance with ID &serviceInstanceId in space &spaceGuid of organization &organizationGuid with parameters &parameters started by &userId*



</td>
</tr>
<tr>
<td valign="top">

Create a new service instance

Action: `create-service-instance-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message: *Creation of service instance with ID &serviceInstanceId in space &spaceGuid of organization &organizationGuid with parameters &parameters completed*



</td>
</tr>
<tr>
<td valign="top">

Create a new service instance

Action: `create-service-instance-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message: *Creation of service instance with ID &serviceInstanceId in space &spaceGuid of organization &organizationGuid with parameters &parameters failed with error message: <error\>*



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance - `requested-to-delete-service-instance`

Action: ``



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion of service instance with ID &serviceInstanceId requested by &userId*



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Action: `about-to-delete-service-instance`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion of service instance with ID &serviceInstanceId started by &userId*



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Action: `delete-service-instance-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion of service instance with ID &serviceInstanceId completed*



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Action: `delete-service-instance-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message: *Deletion of service instance with ID &serviceInstanceId failed with error message: <error\>*



</td>
</tr>
<tr>
<td valign="top">

Update an existing service instance

Action: `about-to-update-service-instance`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-modification`.

Message: *Update of service instance with ID &serviceInstanceId with requested changes &requestedChanges started by &userId*



</td>
</tr>
<tr>
<td valign="top">

Update an existing service instance

Action: `update-service-instance-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-modification`.

Message: *Update of service instance with ID &serviceInstanceId with updated parameters &parameters completed*



</td>
</tr>
<tr>
<td valign="top">

Update an existing service instance

Action: `update-service-instance-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-modification`.

Message: *Update of service instance with ID &serviceInstanceId with updated parameters &parameters failed with error message: <error\>*



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Export tenant data



</td>
<td valign="top">

Action: `about_to_read` 



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-export`.

Message: *User &userId is about to export all data of tenant &tenantDescription.*



</td>
</tr>
<tr>
<td valign="top">

Action: `read` 



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-export`.

Message: *User & userId finished exporting all data of tenant &tenantDescription.*



</td>
</tr>
<tr>
<td valign="top">

Action: `read-failed` 



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-export`.

Message: *Export of all data of tenant &tenantDescription for user &user failed during zip streaming. \[Log-ID: &logId\]*



</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

