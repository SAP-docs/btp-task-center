<!-- loiofe4a8b3be3e84daeb5b73a4b77c5be7e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with the Task List

In the SAP Task Center Web app, you can search for a specific task in the task list, and filter or sort your user tasks by predefined criteria. You can also refresh the task list and personalize the table columns.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_Feedback"/>

## Provide Feedback

Provide your feedback on the SAP Task Center by choosing the feedback icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the upper right corner of the Web app.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_WebAssistant"/>

## Integration with SAP Companion

With the SAP Companion you can see on-screen information, embedded directly in the SAP Task Center Web app.

To open it, choose the SAP Companion icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the upper right corner of the Web app.

> ### Note:  
> This feature must be enabled by your administrator. For more information, see [Create a Task Center Tile](../30-initial-setup/create-a-task-center-tile-70e7f6e.md).



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_Notifications"/>

## Notifications

The notifications must be enabled by your administrator. For more information, see [Enable Notifications for End Users](../40-administration/enable-notifications-for-end-users-caf2543.md).

Once enabled, you start receiving notifications in your SAP Task Center Web app and via email \(if enabled\) whenever a new task is added to your task list.

When you receive a new task, you are notified via the notification icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\), which is updated with the number of notifications. Selecting the notification opens the task details on fullscreen.

You can also be notified via email, if this option is enabled by your administrator and you have selected the email option in your notification settings for the specific task type.

To adjust your notifications settings, go to the user menu and choose <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Settings* \> **<span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Notifications*. For more information, see [Working with Notifications](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/working-with-notifications).

Currently, the notifications displayed in the SAP Task Center Web app and task center in the SAP Mobile Start mobile app are in English, but might contain information in the fallback language, defined by the task provider.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_RefreshTasks"/>

## Refresh Tasks

Choose *Refresh Tasks* to update your task list and synchronize it with the current state of the tasks stored in the SAP Task Center task cache.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_OpenTasks"/>

## Open Task Details

Choose a task from the list to open it in the task details view.

Depending on the type of the selected task, the details view shows the standard user interface or a native user interface for task details.



### Standard User Interface for Task Details

The standard user interface for task details consists of the following areas:

-   Header with the task title, task type, and an *Open in App* button to open the task details in the task provider system
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



The native user interface for task details consists of the following areas:

-   Header with the task title, task type and an *Open in App* button to open the task details in the task provider system
-   Details area with additional information, if available for the selected task. Depending on the task type of the selected task, the details area can contain:
    -   *Details* tab

    -   Second tab for additional details offering line item navigation for further information about each line item record


-   \(Optional\) Footer area with the available actions for the task \(for example *Approve* or *Reject*\)

> ### Note:  
> Depending on configuration done by the task provider, the action buttons in the details area of a task might be displayed in semantic colors as follows:
> 
> -   Green - tasks with positive nature
> 
> -   Red - tasks with negative nature
> 
> -   Gray - tasks with neutral nature
> 
> 
> The nature of the actions is defined by the task providers.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_SortTasks"/>

## Sort Tasks

Use the *Sort* icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) to sort the list of tasks. You can choose between ascending or descending order and other predefined sorting criteria.

> ### Note:  
> The current sorting order is marked by an indicator \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span> or <span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) after the title of the column that has been selected as the sorting criteria.

To be able to sort by custom attributes, you have to first filter by a single task type.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_SearchTasks"/>

## Search and Filter Tasks

Search for tasks using the *Search* field by entering one or more keywords that are included in the *Task Title*.

> ### Note:  
> The search is performed among all tasks that are assigned to the user and stored in the back end. It is applied to the fields listed as hint in the *Search* field. When you filter by a task type with custom attributes, the hint in the *Search* field changes dynamically to reflect the current search, and applies to the custom-attribute columns of data type `string`.

The *Filter* criteria are available in the field above the tasks, next to the *Search* field. By default, you can filter your task list by the following criteria:


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

The *On Behalf Of* filter is only available when you have at least one active substitution rule.

To see the tasks of a user you are substituting, choose the substitution icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the *On Behalf Of* field and choose a name. The list contains only the users you are currently substituting.

Once you choose a user, the following changes appear, corresponding to the enabled substitution:

-   The number of all tasks and tasks in the filter tabs is updated

-   The task list offers only tasks, coming from the substitution

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

Select one or more task types to open their tasks.

Use the *Select All* check box to select all available task types in the list.

The list of task types contains only the task types relevant for the filter tab that you selected, sorted alphabetically. If there are tasks without a task type, then these tasks are grouped into the *Others* category at the end of the *Task Type* filter dropdown list.

The task types, supporting mass actions have an *M* indicator. For more information about processing multiple tasks, see [Working with Multiple Tasks](working-with-multiple-tasks-9f8ef8e.md).

Sometimes tasks with different task IDs might appear with the same task type. In this case, the SAP Task Center Web app appends a number to the end of the task type \(for example *Task Type \(1\)*, *Task Type \(2\)*\) for easier differentiation.

To display the available custom attributes as filters and columns for a specific task, filter by the chosen task type.

> ### Note:  
> Some columns with custom attributes might be hidden for optimal visualization. You can manage the columns from *Personalize* \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).
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

Select a time period from the calender \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

</td>
</tr>
<tr>
<td valign="top">

*Due By* 

</td>
<td valign="top">

Select a date from the calender \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) to review all tasks, that are due before this date.

</td>
</tr>
<tr>
<td valign="top">

\(Optional\) *Confidence Level*

</td>
<td valign="top">

The *Confidence Level* filter provides end users with information about the approval confidence of the tasks, which is calculated by a trained AI model.

If it is enabled by your administrator, the *Confidence Level* filter appears as a custom attribute. To see the filter, choose a *Task Type*, which supports intelligent recommendations, and choose *Go*. In the filter, specify the confidence level range and choose *OK*.

The confidence level is a numerical percentage value ranging from 0 to 100. A higher confidence level encourages positive action on the task, such as approval.

For more information on the task providers supporting the *Intelligent Recommendations* feature, see [Supported Features](../10-what-is/supported-features-257a0ad.md).

For more information on how administrators can enable the *Intelligent Recommendations* feature, see [Working with Intelligent Recommendations](../40-administration/working-with-intelligent-recommendations-340651c.md).

> ### Tip:  
> If the *Confidence Level* column is not available in the task table, although it appears in the filters, use the *Personalize* option \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) to display or rearrange the table columns.



</td>
</tr>
</table>

When you select all the filters you want to apply, choose *Go* to get the result.

You can remove all active filters by choosing *Clear*, or customize the visibility and values of the displayed filters from *Adapt Filters*.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_PersonalizeWebApp"/>

## Personalize the SAP Task Center Web App

To choose which columns are available in the Web app, choose *Personalize* \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) on the right side of the table header. This opens the *Columns* dialog box where you can do the following:

-   Hide and display columns:

    To choose the columns that are displayed, select or deselect their checkboxes in the *Columns* dialog box.

-   Rearrange the order of the columns:

    To change the location of a certain column, select the column and use the up and down arrows on the left side of the header.

-   Search among the column titles:

    To search for a certain column, use the *Search* field in the header.


Choose *OK* to confirm your changes.

> ### Note:  
> The changes that you make to the Web app are persistent. You can use the personalized Web app in another browser or device without having to make the changes again.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_InlineResponse"/>

## Inline Decision Options and Predefined Decision Reasons

The *Actions* column of your task list contains various decision options for easier processing of tasks. You can directly select the first suggested decision option or choose another one from the dropdown list.



### Decision Options

The *Actions* column may contain the following types of actions:

-   Actions defined by task provider


    <table>
    <tr>
    <th valign="top">

    Action
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Result
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Claim*
    
    </td>
    <td valign="top">
    
    Select *Claim* to reserve a task for processing by you.
    
    </td>
    <td valign="top">
    
    -   You get a confirmation that the task is claimed successfully.

    -   The status of the task changes from *Open* to *Reserved*.

    -   You become the processor of the task and the other task recipients no longer have it in their Web app.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Release*
    
    </td>
    <td valign="top">
    
    Choose *Release* to release a task of which you are the processor.
    
    </td>
    <td valign="top">
    
    -   You get a confirmation that the task is released successfully.

    -   The status of the task changes from *Reserved* to *Open*.

    -   You are no longer assigned as the processor of the task.

    -   The other recipients can find the task in their Web app again.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Forward* 
    
    </td>
    <td valign="top">
    
    You can forward tasks to another user for further processing. Please note that in case of embedded UI \(for example, SAP Fiori Elements V.2 object page\), the recipient needs to have the necessary authorizations to the see the embedded UI. Otherwise, the Web app would render the standard user interface for task details.
    
    </td>
    <td valign="top">
    
    The task disappears from the task list of the user who forwards the task and appears in the task list of the recipient in status *Reserved*.

    > ### Note:  
    > In the case where the *Forward* action is not activated in the workflow model, an error could temporary occur when using the *Forward* action for certain SAP Build Process Automation tasks.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Other decision options defined by the task provider
    
    </td>
    <td valign="top">
    
    There might be other decision options if the task provider has preconfigured any \(for example *Approve* or *Reject*\).
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
    For more information, see [Supported Features](../10-what-is/supported-features-257a0ad.md).

    > ### Note:  
    > The labels for *Claim*, *Release* and *Forward* are unified and defined by the Web app, regardless of the label, received by the task provider. Note that these actions may appear in the header or footer in the task details view, depending on the task provider setup.

-   Standard actions \(valid for every task provider\)

    *Open in App* - Choosing this button opens the task in the task provider system.




### Predefined Decision Reasons and Decision Note

For some of the actions \(except for *Claim*, *Release*, *Open in App*\) the task provider may have set up an additional decision popup for a decision reason and decision note. This decision popup may contain:

-   Confirmation text with the chosen action

-   *Decision Reason* - dropdown list with predefined decision reasons

-   Input field labeled as *Decision Note*

-   Footer area with confirmation and cancellation buttons


The decision reason and decision note can be optional or mandatory \(marked with an asterisk \(\*\)\). The confirmation button is active only if the mandatory fields are completed. If these fields are not mandatory, you can submit your decision without adding a decision reason or decision note.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_Display_Cust_Attributes"/>

## Display Custom Attributes

The custom attributes show additional information about a task, depending on the task contextual data. These additional details are exposed as additional columns and allow you to make more informed decisions about tasks, while working with the Web app.



### Procedure

To see the available custom attributes in the Web app, you first need to filter tasks by a single *Task Type*.

Some columns with custom attributes might be hidden for optimal visualization. You can adjust the display of custom attributes, using the Personalize menu \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

> ### Note:  
> Please note that filtering and sorting by a custom attribute, exposing a formatted value is not possible.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_attachments-comments"/>

## Attachments and Comments

To see the attachments and comments, open the task, choose *Show More* and go to the corresponding tab.

You can also upload an attachment or add a comment on these tabs if the functionality is supported by the task provider system.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_Pagination"/>

## Pagination

The Web app list works in growing mode. Initially, the first page loads up to 40 tasks. Additional tasks are loaded in pages of 40 tasks while scrolling towards the end of the page, until all the tasks assigned to the logged in user are displayed.



<a name="loiofe4a8b3be3e84daeb5b73a4b77c5be7e__section_TempInaccess"/>

## Temporarily Inaccessible Tasks

The *Task List* contains only tasks that you can work with. When it is not possible to establish a connection between SAP Task Center and a task provider system, the following notification is displayed in the *Task List* header:

***"Tasks from <Destination Name\> cannot be displayed at the moment. You can refresh your tasks now or try again later. If the problem persists, contact your system administrator.".***

> ### Note:  
> The message can be closed and it will be displayed again only if you refresh the *Task List* and the connection to the task provider system is still not restored.

The inaccessible tasks are filtered out from the *Task List* by the Web app and the task counter takes into account all tasks with live backend connection only.

