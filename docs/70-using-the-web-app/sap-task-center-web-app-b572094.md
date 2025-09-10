<!-- loiob572094a8b584a338e80820d25b0df87 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP Task Center Web App

The SAP Task Center Web app displays all tasks provided by the connected task providers. In the Web app you can view or process the tasks assigned to you, view your completed tasks, or create and manage your substitution rules.



<a name="loiob572094a8b584a338e80820d25b0df87__section_jfk_fkh_tgb"/>

## Prerequisites

To use the SAP Task Center Web app, your administrator must have done the initial setup of SAP Task Center and must have created a Task Center tile on one of the supported central points of entry for accessing applications.



<a name="loiob572094a8b584a338e80820d25b0df87__section_q5k_2kh_tgb"/>

## What Is SAP Task Center Web App?

The SAP Task Center Web app is a unified inbox, which integrates with multiple solutions to provide a seamless and integrated user experience. Tasks from multiple SAP and non-SAP solutions are gathered in one list by the SAP Task Center service and ready to be processed by you.

In the *Inbox* tab of your Web app, you can review all tasks that are assigned to you and process them.

In the *Outbox* tab you can find your completed tasks, task details, comments and attachments.

Additionally, you can set up and manage substitution rules in the *Substitution Management* of SAP Task Center.

You can access the SAP Task Center Web app on a desktop or a mobile device.



### Supported Solutions

For more information on the supported solutions and use cases, see [Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md) and [Supported Features](../10-what-is/supported-features-257a0ad.md).



### Key Features

-   Display the number of tasks from all online connectors in the SAP Task Center Web app.
-   View all tasks that are assigned to you.
-   Use a custom search filter to find the tasks that you want to process.
-   Sort tasks by priority, due date, and status.
-   Filter your tasks by priority, task type, creation date, status, and due date. The task list is limited to the first 1000 entries that match the filter.
-   Filter your tasks based on custom attributes available for tasks.
-   Quickly process your tasks with the help of inline actions available for tasks.
-   View all available information about a task, including the display name of the user, who created the task, or available actions in the details view.
-   Refresh the task list using the *Refresh Tasks* button.
-   Use the *Mass Actions* function to process multiple tasks in parallel.
-   Add and manage your substitutions in the *Substitution Management* view.
-   Create your own views with the preferred filter selection.
-   View your completed tasks in the *Outbox* tab if it's enabled by your administrator.

![An interactive image of the Web app interface. It highlights the main
							elements which you need to be familiar with to use the app.](images/TaskList_5e151cb.png)

![An interactive image of a task's details. Highlights the most important
							actions related to the task.](images/DetailsView_fd3762c.png)



<a name="loiob572094a8b584a338e80820d25b0df87__section_Inbox"/>

## Inbox

> ### Note:  
> The header of the table and the icon tab bar have a sticky behavior so that they are present on top while you scroll the task list.

The columns that are displayed by default in the Web app *Inbox* tab contain the following information about the user tasks:

**Columns Displayed by Default in the SAP Task Center Web App Inbox tab**


<table>
<tr>
<th valign="top">

Column Name

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

\(Optional\) *Processing Errors*

</td>
<td valign="top">

This column appears by default only on the *Failed Tasks* filter tab, if there are failed tasks in the task list. A failed task is a task, for which an attempt to execute an action has failed.

To see details about the failed task, choose the *Processing Errors* icon \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\) in the row of the task.

</td>
</tr>
<tr>
<td valign="top">

*Task*

</td>
<td valign="top">

Task title and additional information about the task as per destination configuration. For more details, see the information related to *tc.ui.label* in [Destinations](../40-administration/destinations-3470733.md).

</td>
</tr>
<tr>
<td valign="top">

*Task Type*

</td>
<td valign="top">

For more information about the supported task types, see [Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md).

This column is not visible by default, but you can unhide it from the *Personalize* button \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

</td>
</tr>
<tr>
<td valign="top">

*Priority*

</td>
<td valign="top">

The priority of the task

</td>
</tr>
<tr>
<td valign="top">

*Created By*

</td>
<td valign="top">

Shows the display name of the user who created the task, if set by the task provider system.

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

The current status of the task

> ### Note:  
> The *Status* column is not displayed on mobile devices.



</td>
</tr>
<tr>
<td valign="top">

*Created On*

</td>
<td valign="top">

Creation date

</td>
</tr>
<tr>
<td valign="top">

*Due*

</td>
<td valign="top">

Due date

</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

Offers the list of possible decision options for a task, for example *Approve* or *Reject*.

Additionally, you can open the task in the task provider, by choosing *Open in App*.

</td>
</tr>
</table>



### Related Information

[Working with the Task List](working-with-the-task-list-fe4a8b3.md)

[Working with Filter Tabs](working-with-filter-tabs-df0aec8.md)

[Working with Multiple Tasks](working-with-multiple-tasks-9f8ef8e.md)

[Working with Views](working-with-views-b446cc8.md)

[Substitution Management](substitution-management-bef9b2d.md)



<a name="loiob572094a8b584a338e80820d25b0df87__section_Outbox"/>

## Outbox

The SAP Task Center Web app outbox is a centralized location where you can view your completed tasks, together with their respective task details, comments, and attachments. In the *Outbox* tab in the Web app you can find tasks completed after the enablement of the outbox.



### Prerequisites

To access the *Outbox* tab, your administrator must have enabled it. For more information, see [SAP Task Center Global Settings](../40-administration/sap-task-center-global-settings-99e5302.md).

> ### Note:  
> Please note that the behavior of Outbox may differ across different task providers. For more information see SAP Note [3582581](https://me.sap.com/notes/3582581).
> 
> For more information on the task providers supporting the *Outbox* feature, see [Supported Features](../10-what-is/supported-features-257a0ad.md).

> ### Note:  
> The header of the table and the icon tab bar have a sticky behavior so that they are present on top while you scroll the task list.

The columns that are displayed by default in the *Outbox* tab contain the following information about the user tasks:

**Columns Displayed by Default in the SAP Task Center Web App Outbox Tab**


<table>
<tr>
<th valign="top">

Column Name

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

*Task*

</td>
<td valign="top">

Task title and additional information about the completed task as per destination configuration. For more details, see the information related to *tc.ui.label* in [Destinations](../40-administration/destinations-3470733.md).

</td>
</tr>
<tr>
<td valign="top">

*Priority*

</td>
<td valign="top">

The priority of the task

</td>
</tr>
<tr>
<td valign="top">

*Completed On*

</td>
<td valign="top">

Completion date

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

The current status of the task. The *Status* column is not displayed on mobile devices.

</td>
</tr>
<tr>
<td valign="top">

*Completed By*

</td>
<td valign="top">

The user who completed the task

</td>
</tr>
<tr>
<td valign="top">

*Created On*

</td>
<td valign="top">

Creation date

</td>
</tr>
<tr>
<td valign="top">

*Due*

</td>
<td valign="top">

Due date

</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

You can open the task in the task provider by choosing *Open in App*.

</td>
</tr>
</table>



### Related Information

[Working with the Task List](working-with-the-task-list-fe4a8b3.md)

[Working with Filter Tabs](working-with-filter-tabs-df0aec8.md)

[Working with Views](working-with-views-b446cc8.md)

