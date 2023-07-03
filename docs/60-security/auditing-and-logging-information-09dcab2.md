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

Message:

Creation of data for <account\> completed



</td>
</tr>
<tr>
<td valign="top">

Create new tenant

Action: `create-account-data-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message:

Creation of data for <account\> failed. Reason for failing the creation is <Reason\>



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `requested-to-delete-account-data`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion \(reason: <reason\>\) of data for <account\> requested by <user\>



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `about-to-delete-account-data`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion \(reason: <reason\>\) of data for <account\> started by <user\>



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `delete-account-data-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion \(reason: <reason\>\) of data for <account\> completed



</td>
</tr>
<tr>
<td valign="top">

Delete existing tenant

Action: `delete-account-data-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion \(reason: <reason\>\) of data for <account\> failed. Reason for failing the deletion is <Reason\>



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

Message:

Creation of service instance with ID &serviceInstanceId in space &spaceGuid of organization &organizationGuid with parameters &parameters started by &userId



</td>
</tr>
<tr>
<td valign="top">

Create a new service instance

Action: `create-service-instance-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message:

Creation of service instance with ID &serviceInstanceId in space &spaceGuid of organization &organizationGuid with parameters &parameters completed



</td>
</tr>
<tr>
<td valign="top">

Create a new service instance

Action: `create-service-instance-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-creation`.

Message:

Creation of service instance with ID &serviceInstanceId in space &spaceGuid of organization &organizationGuid with parameters &parameters failed with error message: <error\>



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance - `requested-to-delete-service-instance`

Action: ``



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion of service instance with ID &serviceInstanceId requested by &userId



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Action: `about-to-delete-service-instance`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion of service instance with ID &serviceInstanceId started by &userId



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Action: `delete-service-instance-done`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion of service instance with ID &serviceInstanceId completed



</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Action: `delete-service-instance-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-termination`.

Message:

Deletion of service instance with ID &serviceInstanceId failed with error message: <error\>



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

Message:

Update of service instance with ID &serviceInstanceId with updated parameters &parameters completed



</td>
</tr>
<tr>
<td valign="top">

Update an existing service instance

Action: `update-service-instance-failed`



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-modification`.

Message:

Update of service instance with ID &serviceInstanceId with updated parameters &parameters failed with error message: <error\>



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

Message:

User &userId is about to export all data of tenant &tenantDescription.



</td>
</tr>
<tr>
<td valign="top">

Action: `read` 



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-export`.

Message:

User & userId finished exporting all data of tenant &tenantDescription.



</td>
</tr>
<tr>
<td valign="top">

Action: `read-failed` 



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `data-export`.

Message:

Export of all data of tenant &tenantDescription for user &user failed during zip streaming. \[Log-ID: &logId\]



</td>
</tr>
<tr>
<td valign="top">

Reconciliation



</td>
<td valign="top">

Action: `reconciliation-job-executed` 



</td>
<td valign="top">

Entries are logged as `SecurityEventAuditMessage`, sub-category `Reconciliation`.

Message:

A reconciliation job has been started for tenant &tenantId.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Substitution Management



</td>
<td valign="top">

Action: `created` 



</td>
<td valign="top">

Entries are logged as `DataModificationEventAuditMessage`, sub-category `audit.data-modification`.

Message:

Data Modification message. Attribute with name "SubstitutionRule" was changed from "" to "\{ "urn" : "example-urn", "applicationId" : "exampleApplicationId", "applicationInstanceId" : "example-applicationInstanceId", "tenantId" : "example-tenantId", "localId" : "example-localId", "principal" : "example-principal", "substitute" : "example-substitute", "validFrom" : "validFromDate", "validTo" : "validToDate", "infoMessage" : "Created successfuly", "infoUrl" : null, "principalName" : "None", "substituteName" : "example-substituteName", "applicationUrn" : "example-applicationUrn", "status" : "OK" \}". The attribute is a part of an object with type "Substitution" and id consisting of: urn "example-urn". It belongs to a subject with type "User", and id consisting of: userUUID "example-userUUID". Custom details: "auditLogMessage" with value "The substitution rule for SAP Task Center tenant with tenantId=example-tenantId having the listed parameters has been created by user with userId=example-userId";



</td>
</tr>
<tr>
<td valign="top">

Action: `deleted` 



</td>
<td valign="top">

Entries are logged as `DataModificationEventAuditMessage`, sub-category `audit.data-modification`.

Message:

Data Modification message. Attribute with name "SubstitutionRule" was changed from "\{ "urn" : "example-urn", "applicationId" : "exampleApplicationId", "applicationInstanceId" : "example-applicationInstanceId", "tenantId" : "example-tenantId", "localId" : "example-localId", "principal" : "example-principal", "substitute" : "example-substitute", "validFrom" : "validFromDate", "validTo" : "validToDate", "infoMessage" : "Created successfully", "infoUrl" : null, "applicationUrn" : "example-applicationUrn", "status" : "OK" \}" to "". The attribute is a part of an object with type "Substitution" and id consisting of: urn "example-urn". It belongs to a subject with type "User", and id consisting of: userUUID "example-userUUID". Custom details: "auditLogMessage" with value "The substitution rule for SAP Task Center tenant with tenantId=example-tenantId having the listed parameters has been deleted by user with userId=example-userID";



</td>
</tr>
<tr>
<td valign="top">

Action: `repaired` 



</td>
<td valign="top">

Entries are logged as `DataModificationEventAuditMessage`, sub-category `audit.data-modification`.

Message:

Data Modification message. Attribute with name "SubstitutionRule" was changed from "\{ "urn" : "example-urn", "applicationId" : "exampleApplicationId", "applicationInstanceId" : "example-applicationInstanceId", "tenantId" : "example-tenantId", "localId" : "example-localId", "principal" : "example-principal", "substitute" : "example-substitute", "validFrom" : "validFromDate", "validTo" : "validToDate", "infoMessage" : "Created successfully", "infoUrl" : null, "applicationUrn" : "example-applicationUrn", "status" : "OK" \}" to "\{ "urn" : "example-urn", "applicationId" : "example-applicationId", "applicationInstanceId" : "example-applicationInstanceId", "tenantId" : "example-tenantId", "localId" : "example-localId", "principal" : "example-localId", "substitute" : "example-substitute", "validFrom" : "validFromDate", "validTo" : "validToDate", "infoMessage" : "Created successfully", "infoUrl" : null, "applicationUrn" : "example-applicationUrn", "status" : "OK" \}". The attribute is a part of an object with type "Substitution" and id consisting of: urn "example-Urn". It belongs to a subject with type "User", and id consisting of: userUUID "example-userUUID". Custom details: "auditLogMessage" with value "The substitution rule for SAP Task Center tenant with tenantId=example-tenantId having the listed parameters has been repaired by user with userId=example-userID";



</td>
</tr>
<tr>
<td valign="top">

Action: `accessed` 



</td>
<td valign="top">

Entries are logged as `DataAccessEventAuditMessage`, sub-category `audit.data-access`.

Message:

Data Access message. Attribute with name "userUUID" was read. Attribute with name "displayName" was read. Attribute with name "locale" was read. Attribute with name "email" was read. The attributes are a part of an object with type "UserDetails" and id consisting of: userId "<userUUID\>". They belong to a subject with type "User", and id consisting of: userId "<userUUID\>". Custom details: "auditLogMessage" with value "User with userId=example-userID has accessed user data by using SAP Task Center tenant with tenantId=example-tenantId. 8 records have been returned for the "; "searchParameters" with value "example-searchParameters";



</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

