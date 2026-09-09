<!-- loioac890941868349e59aef541c8a9a8818 -->

# Notification Settings Tab

Manage the notifications for end users from the SAP Task Center Administration app.

The SAP Task Center Administration app allows you to manage notification settings for your task providers in the *Notification Settings* tab.

When you modify the properties in the SAP Task Center Administration app, this change is automatically synchronized with the task provider's destination in the SAP BTP Cockpit. The same applies in reverse - when you modify the properties in the task provider's destination in the SAP BTP Cockpit, the change is automatically synchronized with the SAP Task Center Administration app.



## Prerequisites

You have enabled notifications for end users as described in [Enable Notifications for End Users](enable-notifications-for-end-users-caf2543.md).



## Using the Notification Settings Tab

To enable and customize the notifications, select a task provider under *Connectors*. The *Notification Settings* tab allows you to modify the following properties for each task provider:

**Properties in the Notification Settings Tab**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Notifications

</td>
<td valign="top">

Enable or disable notifications for the selected task provider. Once enabled, the notifications apply to all end users.

> ### Note:  
> You configure the notification settings individually per connector. Each task provider is managed independently.



</td>
</tr>
<tr>
<td valign="top">

Email Notifications

</td>
<td valign="top">

Manage email notifications for new task types and notification types from a selected task provider. Once enabled, all end users receive email notifications unless they modify their individual notification preferences.

> ### Note:  
> If you want the end users to receive email notifications for existing task types and notification types, you need to remove the *tc.enabled* property from the task provider's destination and add it again after a few minutes, as described in [Repopulate the Task Cache](repopulate-the-task-cache-e93aa71.md).
> 
> Keep in mind that by doing so, all notifications and notification types associated with the task provider will be unregistered. This results in the loss of notifications and personal user settings.



</td>
</tr>
<tr>
<td valign="top">

Overdue Tasks

</td>
<td valign="top">

Enable notifications for tasks that are overdue. End users can receive the notifications via the Web app, mobile, or email \(if enabled\).

You can set the number of hours after the due date passes to send a notification. By default, the value is set to `8` hours.

> ### Note:  
> End users can receive this type of notification only if the task has a due date.



</td>
</tr>
<tr>
<td valign="top">

Due Date Reminder

</td>
<td valign="top">

Enable notifications for tasks whose due date is approaching. End users can receive the notifications via the Web app, mobile, or by email \(if enabled\).

You can set the number of hours before the due date passes to send a notification. By default, the value is set to `8` hours.

> ### Note:  
> End users can receive this type of notification only if the task has a due date, and the due date has passed not more than 2 days prior.



</td>
</tr>
</table>

For more information on each property, see the respective task provider topic in [Integrate SAP Task Center with Task Providers](../integrate-sap-task-center-with-task-providers-b158111.md).

