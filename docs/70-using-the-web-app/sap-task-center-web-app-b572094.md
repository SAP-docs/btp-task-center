<!-- loiob572094a8b584a338e80820d25b0df87 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP Task Center Web App

The SAP Task Center Web app displays all the tasks provided by the SAP Task Center service. You can process workflow tasks in the Web app, which runs on SAP Build Work Zone, standard edition.



<a name="loiob572094a8b584a338e80820d25b0df87__section_jfk_fkh_tgb"/>

## Prerequisites

To use the SAP Task Center Web app, your administrator must have created a *SAP Task Center* tile on one of the supported central points of entry for accessing apps.



<a name="loiob572094a8b584a338e80820d25b0df87__section_q5k_2kh_tgb"/>

## What Is SAP Task Center Web App?

The SAP Task Center is a new unified inbox for approvals across multiple applications with a seamless and integrated user experience. Workflow tasks from multiple SAP solutions are gathered in one list by the SAP Task Center service and ready to be processed with just one click. In the Web app, you can view all workflow tasks that are assigned to you and process them. A workflow task is a type of workflow object that is visualized in the Web app.

You can use the Web app on a desktop or a mobile device. The app displays all the tasks that are assigned to you. The task list is organized in tabs. For more information, see [Working with Filter Tabs](working-with-filter-tabs-df0aec8.md).

> ### Note:  
> The header of the table and the icon tab bar have a sticky behavior. This allows you to scroll the task list and have them visible at the same time.

The columns that are displayed by default in the Web app contain the following information about the user tasks:

**Columns Displayed by Default in the SAP Task Center Web App**


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

To see details about the failed task, choose the *Processing Errors* icon \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) in the row of the task.



</td>
</tr>
<tr>
<td valign="top">

*Task*



</td>
<td valign="top">

Task title and additional information about the task as per destination configuration. For more information, see the information related to *tc.ui.label* in [Destinations](../40-administration/destinations-3470733.md).



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

Shows the display name of the user, who created the task, if set by the task provider system.



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

Displays the list of possible decision options for a task, for example *Approve* or *Reject*.

Additionally, you can open the task in the task provider, by choosing *Open in App*.



</td>
</tr>
</table>



<a name="loiob572094a8b584a338e80820d25b0df87__section_rpf_wpl_rpb"/>

## Supported Solutions

See [Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md).



<a name="loiob572094a8b584a338e80820d25b0df87__section_apl_psc_zz"/>

## Key Features

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

**Related Information**  


[Working with the Task List](working-with-the-task-list-fe4a8b3.md "In the SAP Task Center Web app, you can search for a specific task in the task list, and filter or sort your user tasks by predefined criteria. You can also refresh the task list and personalize the table columns.")

[Working with Filter Tabs](working-with-filter-tabs-df0aec8.md "Filter tabs organize your tasks in prefiltered semantic groups for better efficiency.")

[Working with Multiple Tasks](working-with-multiple-tasks-9f8ef8e.md "You can process multiple tasks at once, by using the Mass Actions functionality.")

[Substitution Management](substitution-management-bef9b2d.md "Use Substitution Management to view and maintain your substitutions.")

