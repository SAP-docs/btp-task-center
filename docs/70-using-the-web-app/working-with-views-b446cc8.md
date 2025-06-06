<!-- loiob446cc82948e43b6ad00562b8d3f8609 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with Views

Create, store, access customized search filters in views to easily access the tasks you would like to work on.



<a name="loiob446cc82948e43b6ad00562b8d3f8609__section_lpg_qph_kyb"/>

## Context

In the SAP Task Center Web app, you can store customized filters in personalized views for an easier access to the targeted tasks. Additionally, you can store the sort order of the task list in a view, or open a public view with filter criteria, predefined by key users in your organization.

> ### Example:  
> Here are a few example use cases for private or public views:
> 
> -   Store your tasks with *High* priority in a view.
> 
> -   Open a public view, created by a key user, to filter by predefined criteria.



### Default View

The *Standard* view is the default view, initially available in the SAP Task Center Web app.

If you make changes to the filter options, which affect the standard view, the view is marked with an asterisk \(\*\) to indicate the unsaved changes, and you can save your personalized filter as a new view.

There can be only one default view, which you can change in the *Manage Views* dialog, or when saving a new view.

If you change the default view, you can open it from the dropdown list of views \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\), or reload the current page.

> ### Remember:  
> The *Inbox* and *Outbox* tabs share the same list of views. Any new custom views you create in either tab will automatically appear in the dropdown list of views in both tabs. Custom views are not shared between the tabs, so a view created in one tab does not apply to the other.
> 
> Each tab has its own *Standard* view, which appears only once in the list.



<a name="loiob446cc82948e43b6ad00562b8d3f8609__section_hbb_hpm_jyb"/>

## Create New View

You can create a personalized view, based on any of the options, displayed on the filter bar of the SAP Task Center Web app, including *Search* and *On Behalf Of* option. For more details on the *On Behalf Of* option, see [Working with the Task List](working-with-the-task-list-fe4a8b3.md).

1.  In your Web app, make the desired selection on filter tab, filter, search options, or sorting.

    The current view \(*Standard* is default\) is marked with an asterisk \(\*\) to indicate the unsaved changes.

2.  Open the dropdown, next to the name of the current view \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\) and choose *Save As*.

3.  In the *Save View* window, add the name of your personalized view, choose if you want to make a default view, and save it.


> ### Tip:  
> To keep your views organized and easily identifiable, it's good practice to include `Inbox` or `Outbox` in the name of each custom view you create. This will help you to quickly determine which tab the view is related to.



<a name="loiob446cc82948e43b6ad00562b8d3f8609__section_p51_3pm_jyb"/>

## Open a View

1.  Open the dropdown, next to the name of the current view \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\).

    In *My Views* you get the list of your views, including the default view and the views, marked as favorites by you.

2.  Choose a view from the list.

    When you select a view, it automatically loads your tasks in the Web app. The saved preferences on your task list, as well as filter tab, and additional filters are automatically applied.

    When you select a view, it automatically loads your tasks in the Web app. The saved preferences on *Inbox* or *Outbox*, as well as filter tab, and additional filters are automatically applied.




<a name="loiob446cc82948e43b6ad00562b8d3f8609__section_kfb_cvr_kyb"/>

## Manage Views

To check the details of existing private or public views, to rename them, or to set your default and favorite views, which to be displayed in the dropdown list, open the list of views from the dropdown \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\), choose *My Views* \> *Manage*, and make your changes.

To access public views, they must have already been set up by key users. For more information, see [Creating Public Views for End Users](../40-administration/creating-public-views-for-end-users-4c2c2af.md).

> ### Note:  
> Currently, users with key user roles can create public views only based on tasks and task types for which they are assigned as processors.

Choosing a public view as favorite, personalizing it, or making it default view will only make it appear in your personal preferences, but does not affect the preferences of others.

