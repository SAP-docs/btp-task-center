<!-- loiofe4a8b3be3e84daeb5b73a4b77c5be7e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with the Task List

In the SAP Task Center Web app, you can search for a specific task in the task list, and filter or sort your user tasks by predefined criteria. You can also refresh the task list and personalize the table columns.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_WebAssistant"/>

## Integration with SAP Companion

With the SAP Companion you can see on-screen information, embedded directly in the SAP Task Center Web app.

To open it, choose the SAP Companion icon \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) in the upper right corner of the Web app.

> ### Note:  
> This feature must be enabled by your administrator. For more information, see [Create a Task Center Tile on SAP Build Work Zone, Standard Edition](../30-initial-setup/create-a-task-center-tile-on-sap-build-work-zone-standard-edition-1f89381.md).
> 
> You can either use the SAP Companion for SAP Task Center or SAP Companion for SAP Build Work Zone, standard edition, depending on the setup or your system.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_RefreshTasks"/>

## Refresh Tasks

Choose *Refresh Tasks* to update your task list and synchronize it with the current state of the tasks stored in the SAP Task Center task cache.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_OpenTasks"/>

## Open Task Details

Choose a task from the list to open it in the task details view.

Depending on the type of the selected task, the details view shows the standard user interface or a native user interface for task details.



### Standard User Interface for Task Details

The standard user interface for task details consists the following areas:

-   Header with the task title, task type and an *Open in App* button to open the task details in the task provider system
-   Details area with additional information, if available for the selected task
-   \(Optional\) Footer area with the available actions for the task \(for example *Approve* or *Reject*\)



### Native User Interface for Task Details

The SAP Task Center Web app provides a tailored view for displaying the task details for a few task types. Those native user interfaces for task details provide substantially more contextual information about the task compared to the standard user interfaces for task details, so an approver can perform a decision about the task based on that latter relevant information.

The supported task types for which native task details user interfaces are provided by the SAP Task Center are:

-   SAP Ariba

    -   Purchase Requisitions \(SAP Ariba Buying\)

    -   Procurement Invoice Approvals \(SAP Ariba Buying\)


-   SAP Concur

    -   Expense Reports

    -   Travel Requests


-   SAP SuccessFactors

    -   Time Off Approvals

    -   Time Sheet Approvals


-   SAP Fieldglass

    -   Job Posting Approvals

    -   Work Order Approvals



The native user interface for task details consists the following areas:

-   Header with the task title, task type and an *Open in App* button to open the task details in the task provider system
-   Details area with additional information, if available for the selected task. Depending on the task type of the selected task, the details area can contain:
    -   *Details* tab

    -   Second tab for additional details offering line item navigation for further information about each line item record

    -   \(Optional\) *History* tab with a chronological view on the events related to the selected task


-   \(Optional\) Footer area with the available actions for the task \(for example *Approve* or *Reject*\)



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_SortTasks"/>

## Sort Tasks

Use the *Sort* icon \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) to sort the list of tasks. You can choose between ascending or descending order and other predefined sorting criteria.

> ### Note:  
> The current sorting order is marked by an indicator \(<span style="color:#346187;"><span class="SAP-icons"></span></span> or <span style="color:#346187;"><span class="SAP-icons"></span></span>\) after the title of the column that has been selected as the sorting criteria.

To be able to sort by custom attributes, you have to first filter by a single task type.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_SearchTasks"/>

## Search for Tasks

Search for tasks using the *Search* field by entering one or more keywords that are included in the *Task Title*.

> ### Note:  
> The search is performed among all tasks that are assigned to the user and stored in the back end. It is applies to the fields listed as hint in the *Search* field. When you filter by a task type with custom attributes, the hint in the *Search* field changes dynamically to reflect the current search, and applies to the custom-attribute columns of data type `string`.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_FilterTasks"/>

## Filter Tasks

The *Filter* criteria are displayed in the field above the tasks, next to the *Search* field. By default, you can filter your task list by the following criteria:


<table>
<tr>
<th valign="top">

Filter By



</th>
<th valign="top">

Details



</th>
</tr>
<tr>
<td valign="top">

\(Optional\) *On Behalf Of*



</td>
<td valign="top">

The *On Behalf Of* filter is only visible when you have at least one active substitution rule.

To see the tasks of a user you are substituting, choose the substitution icon \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) in the *On Behalf Of* field and choose a name. The list contains only the users you are currently substituting.

Once you choose a user, the following changes appear, corresponding to the enabled substitution:

-   The number of all tasks and tasks in the filter tabs is updated

-   The task list displays only tasks, coming from the substitution

-   The preselected filters are cleared

-   Sorting is cleared

-   The task types are updated according to the substitution

-   *Refresh Tasks* refreshes the list of tasks coming from the substitution

-   If you choose *Clear*, the *On Behalf Of* filter remains unchanged


To go back to the list of your tasks, clear the *On Behalf Of* filter.



</td>
</tr>
<tr>
<td valign="top">

*Task Type* 



</td>
<td valign="top">

Select one or more task types to display their tasks.

The list of task types contains only the task types relevant for the filter tab that you selected, sorted alphabetically. If there are tasks without a task type, then these tasks are grouped into the *Others* category at the bottom of the *Task Type* filter dropdown list.

Sometimes tasks with different task IDs might appear with the same task type. In this case, the SAP Task Center Web app appends a number to the end of the task type \(for example *Task Type \(1\)*, *Task Type \(2\)*\) for easier differentiation.

To display the available custom attributes as filters and columns for a specific task, filter by the chosen task type.

> ### Note:  
> Some columns with custom attributes might be hidden for optimal visualization. You can manage the columns from Personalize \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\).
> 
> To filter by custom attributes, select only one task type.



</td>
</tr>
<tr>
<td valign="top">

*Priority*



</td>
<td valign="top">

Select one or more of the following categories: *Low*, *Medium*, *High*, or *Very High*.



</td>
</tr>
<tr>
<td valign="top">

*Status* 



</td>
<td valign="top">

Select one or more of the following categories: *Open*, *Reserved* or *In Progress*.



</td>
</tr>
<tr>
<td valign="top">

*Created Within* 



</td>
<td valign="top">

Select a time period from the calender \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\).



</td>
</tr>
<tr>
<td valign="top">

*Due By* 



</td>
<td valign="top">

Select a date from the calender \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) to display all tasks, that are due before this date.



</td>
</tr>
</table>

When you select all the filters you want to apply, choose *Go* to see the result.

You can remove all active filters by choosing *Clear*, or customize the visibility and values of the displayed filters from *Adapt Filters*.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_PersonalizeWebApp"/>

## Personalize the SAP Task Center Web App

To choose which columns are displayed in the Web app, choose *Personalize* \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) on the right side of the table header. This opens the *Columns* dialog box where you can do the following:

-   Hide and display columns:

    To choose the columns that are displayed, select or deselect their checkboxes in the *Columns* dialog box.

-   Rearrange the order of the columns:

    To change the place in which a certain column is displayed, select the column and use the up and down arrows on the left side of the header.

-   Search among the column titles:

    To search for a certain column, use the *Search* field in the header.


Choose *OK* to confirm your changes.

> ### Note:  
> The changes that you make to the Web app are persistent. You can use the personalized Web app in another browser or device without having to make the changes again.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_InlineResponse"/>

## Inline Decision Options and Predefined Decision Reasons

The *Actions* column of your task list contains the *Open in App* button, which opens the task in the task provider system, and may contain decision options, preconfigured by the task provider, for example *Approve* or *Reject*. You can directly choose the displayed decision option, or choose another one from the dropdown list. When you select one of the options, a decision pop-up with the following content appears:

-   Confirmation text with the chosen action

-   Footer area with *Submit* and *Cancel* buttons


Depending on the task configuration, following might be displayed as well:

-   *Decision Reason* dropdown list with predefined decision reasons

-   Input field labeled as *Decision Note*


The decision reason and decision note can be optional or mandatory \(marked with an asterisk \(\*\)\). The *Submit* button is active only if the mandatory fields are completed. If these fields are not mandatory, you can submit your decision without adding a decision reason or decision note.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_Display_Cust_Attributes"/>

## Display Custom Attributes

The custom attributes show additional information about a task, depending on the task contextual data. These additional details are exposed as additional columns and allow you to make more informed decisions about tasks, while working with the Web app.



### Procedure

To see the available custom attributes in the Web app, you first need to filter tasks by a single *Task Type*.

Some columns with custom attributes might be hidden for optimal visualization. You can adjust the display of custom attributes, using the Personalize menu \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\).



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_attachments-comments"/>

## Attachments and Comments

To see the attachments and comments, open the task, choose *Show More* and go to the corresponding tab.

You can also upload an attachment or add a comment on these tabs if the functionality is supported by the task provider system.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_Pagination"/>

## Pagination

The Web app list works in growing mode. Initially, the first page loads up to 40 tasks. Additional tasks are loaded in pages of 40 tasks while scrolling down, until all the tasks assigned to the logged in user are displayed.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_TempInaccess"/>

## Temporarily Inaccessible Tasks

The *Task List* contains only tasks that you can work with. When it is not possible to establish a connection between SAP Task Center and a task provider system, the following notification is displayed in the *Task List* header:

***"Tasks from <Destination Name\> cannot be displayed at the moment. You can refresh your tasks now or try again later. If the problem persists, contact your system administrator.".***

> ### Note:  
> The message can be closed and it will be displayed again only if you refresh the *Task List* and the connection to the task provider system is still not restored.

The inaccessible tasks are filtered out from the *Task List* by the Web app and the task counter displays all tasks with live backend connection only.

