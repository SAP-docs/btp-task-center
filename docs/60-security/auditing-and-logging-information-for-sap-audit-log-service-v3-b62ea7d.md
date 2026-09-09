<!-- loiob62ea7dabdd848d7afd0ee51ce9ab40c -->

# Auditing and Logging Information for SAP Audit Log Service V3

Here you can find a list of the security events that are logged by the SAP Task Center service.



> ### Note:  
> V3 is not available for Sovereign Clouds \(for example, cf-us50-canary\) and in cf-uk20.

**Security Events Written in Audit Logs**


<table>
<tr>
<th valign="top">

Event Grouping

</th>
<th valign="top">

What Events are Logged

</th>
<th valign="top">

How to Identify Related Log Events

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Instance events

</td>
<td valign="top">

Access an existing service instance

Event: `BACKUP_AND_RESTORE`

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataAccess`.

Message:

The attribute “attribute” of Object Type “object-type” with Object ID <objectID\> has been accessed via Channel ID <channelID\> \(Channel Type “channel-type”\). The read value is \{"status":"value","backupCount":"count"\}.

</td>
</tr>
<tr>
<td valign="top">

Delete an existing service instance

Event: `backup-deletion`

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataDelete`.

Message:

The attribute “attribute” of Object ID <objectID\> \(Object Type “object-type”\) with value “value” has been deleted.

</td>
</tr>
<tr>
<td valign="top">

Tenant events

</td>
<td valign="top">

Event: `modification`

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `cmkTenantModification`.

Message:

Tenant with ID <tenantID\> \(Customer Tenant Context ID: <systemID\>\) has been modified. Action = "cmkAction" for Customer Managed Key <cmkID\>.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Export tenant data

</td>
<td valign="top">

Event: `read` 

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataExport`.

Message:

Object ID <objectID\> \(Object Type “object-type”\) has been exported via Channel ID <channeID\>. Destination URI: <URI\>.

</td>
</tr>
<tr>
<td valign="top">

Event: `download-done` 

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataExport`.

Message:

Object ID <objectID\> \(Object Type “object-type”\) has been exported via Channel ID <channeID\>. Destination URI: <URI\> .

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Substitution Management

</td>
<td valign="top">

Event: `created` 

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataCreate`.

Message:

The attribute “attribute” with Object ID <objectID\> of Object Type “object-type” with value “value” has been created.

</td>
</tr>
<tr>
<td valign="top">

Event: `deleted` 

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataDelete`.

Message:

The attribute “attribute” of Object ID <objectID\> \(Object Type “object-type”\) with value “example-value” has been deleted.

</td>
</tr>
<tr>
<td valign="top">

Event: `repaired` 

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataModification`.

Message:

The attribute “attribute” of Object ID <objectID\> \(Object Type “object-type”\) has been changed from value “old-value” to new value “new-value”.

</td>
</tr>
<tr>
<td valign="top">

Event: `accessed` 

</td>
<td valign="top">

Entries are logged as `CloudEvent`, event type `dataAccessed`.

Message:

The attribute “attribute” of Object Type “object-type” tenant data with Object ID <objectID\> has been accessed via Channel ID <channeID\> \(Channel Type “channel-type”\). The read value is “value”.

</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[What is SAP Audit Log Viewer Service in SAP for Me](https://help.sap.com/docs/AUDIT_LOG_VIEWER/c3f8b96450e443cebbdc9c2d162b86fa/735d365216c849389cfed538936683e3.html?ai=true&version=Cloud)

