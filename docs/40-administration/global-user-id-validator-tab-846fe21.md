<!-- loio846fe2119fe447f1a133295b7d7f0ed1 -->

# Global User ID Validator Tab

Validate the *Global User IDs* of end users from the SAP Task Center Administration app.

After the initial setup, end users might not receive their tasks because the *Global User ID* is not configured in Identity Authentication. As an administrator, you can validate whether the *Global User ID* has been set up correctly and whether any additional steps are required. This validation can also be performed manually by following the [Troubleshooting a Task at SAP Task Center \(For Administrators\)](../80-troubleshooting/troubleshooting-a-task-at-sap-task-center-for-administrators-2f26551.md).

> ### Note:  
> Before using the *Global User ID* tab, make sure that the status of the connector is OK. For more information, see [Connector Monitoring Tab](connector-monitoring-tab-dac4bef.md).



## Working with the Global User ID Validator Tab

Select the *Start Validation* button and select a task provider.

On the *Global User ID Validator* tab you can find information about:

-   The tasks for the selected task provider
-   Task type of all displayed tasks
-   Creation of the tasks
-   Status of the tasks
-   Validation status of the tasks

> ### Note:  
> For testing purposes, you can access and validate only the most recent up to 10 tasks from the selected task provider. These tasks may belong to different end users. Please note that tasks with status *Completed* have already been processed and may not appear in the *Inbox* of the user.

> ### Note:  
> The table does not update automatically after changes are made. Select the *Refresh* button to reload the table manually.



## Task View

Select a task from the *Global User ID Validator* table to open the Task View. This view shows the users and groups assigned to the task and their validation status.

**Individual Recipients**


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

OK

</td>
<td valign="top">

The *Global User ID* of the user is correct.

</td>
</tr>
<tr>
<td valign="top">

Missing

</td>
<td valign="top">

The *Global User ID* or the email of the user is missing. For more information, see [**List of Integration Scenarios**](https://help.sap.com/docs/cloud-identity/system-integration-guide/list-of-integration-scenarios?version=Cloud&ai=true) and [**List and Edit User Details**](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/list-and-edit-user-details?version=Cloud&ai=true).

</td>
</tr>
<tr>
<td valign="top">

Invalid

</td>
<td valign="top">

The user with that *Global User ID* cannot be found in SAP Cloud Identity Services. Make sure that you have entered correct email and *Global User ID*. For more information, see [**Global User ID in Integration Scenarios**](https://help.sap.com/docs/cloud-identity/system-integration-guide/global-user-id-in-integration-scenarios?version=Cloud&ai=true).

</td>
</tr>
</table>

**User Groups**

-   OK - The group was successfully resolved in SAP Cloud Identity Services.
-   Invalid - The group cannot be found in SAP Cloud Identity Services.

A Task Processor is the user or user group currently working on the task. A task can be open to everyone, in which case no task processor is assigned.

**Task Processor**


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

OK

</td>
<td valign="top">

The task processor is found in SAP Cloud Identity Services.

</td>
</tr>
<tr>
<td valign="top">

Invalid

</td>
<td valign="top">

The task processor's *Global User ID* cannot be found in SAP Cloud Identity Services.

</td>
</tr>
<tr>
<td valign="top">

Not found

</td>
<td valign="top">

No task processor is assigned to the task.

</td>
</tr>
</table>

