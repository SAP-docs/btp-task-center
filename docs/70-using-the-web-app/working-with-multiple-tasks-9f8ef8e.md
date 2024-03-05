<!-- loio9f8ef8e63e4549de8b79b667b202aa42 -->

# Working with Multiple Tasks

You can process multiple tasks at once, by using the *Mass Actions* functionality.



<a name="loio9f8ef8e63e4549de8b79b667b202aa42__section_mqj_wny_z5b"/>

## Enable *Mass Actions*

To enable the *Mass Actions* functionality, you must filter the task list by a single task type that supports mass actions, or there must be only one task type available in the list.

The task types, supporting mass actions have an *M* indicator next to the task type name.

When you filter by a single task type, that supports mass actions, *Mass Actions* become enabled and you can select multiple tasks in the task list.

If you select the *Select All* checkbox, only the loaded tasks on the current page are selected. You can select and process up to 2000 tasks.

For more information on the task providers, supporting *Mass Actions*, see [Supported Features](../10-what-is/supported-features-257a0ad.md).



<a name="loio9f8ef8e63e4549de8b79b667b202aa42__section_rbj_wj2_1vb"/>

## Process Multiple Tasks

To perform mass actions on a set of tasks, proceed as follows:

1.  Select the tasks that you want to process in parallel.

2.  Choose an action from the *Mass Actions* dropdown list.

3.  \(Optional\) Add a *Decision Reason*.

4.  \(Optional\) Add a *Decision Note*.

    The *Decision Reason* and *Decision Note* will be applied to all tasks, processed by the mass action.

    For more information about the decision reason and decision note, see [Working with the Task List](working-with-the-task-list-fe4a8b3.md).

5.  Submit your decision.

    As result, you receive a confirmation that the tasks are successfully processed.

    > ### Note:  
    > In case that some of the tasks cannot be processed, before completing the action you receive a list of these tasks and the information, that they are skipped. All decisions performed by the mass action are processed asynchronously in SAP Task Center.
    > 
    > Once you have completed the action, if there was a failure in processing some of the tasks at the task provider side, you can find more details on the *Failed Tasks* filter tab. For more information, see [Working with Filter Tabs](working-with-filter-tabs-df0aec8.md).




<a name="loio9f8ef8e63e4549de8b79b667b202aa42__section_cvg_4k2_1vb"/>

## Tips

-   If the options below *Mass Actions* are disabled, make sure that you have selected at least one task.

-   You can select and process up to 2000 tasks from the list for mass processing at a time.

-   The *Mass Actions* functionality must be enabled by the task provider for the selected task type.

-   If you choose an inline response option to a task, the response option is applied only to this task.


