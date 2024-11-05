<!-- loio2f26551a8d9f40d98beb75a1e13ea221 -->

# Troubleshooting a Task at SAP Task Center \(For Administrators\)

Steps for SAP Task Center Administrators to troubleshoot and resolve issues related to task processing.



<a name="loio2f26551a8d9f40d98beb75a1e13ea221__section_ufm_ksw_rbc"/>

## A task is not available in the SAP Task Center Web App task list of a user

**Troubleshooting Steps:**



### 1. Check if all prerequisites are completed.

Make sure that all prerequisites in [Initial Setup](../30-initial-setup/initial-setup-8347694.md#loio834769400794464489f390350a82bbd6__section_rvy_tcp_pzb) are completed. Pay specific attention to the part about [Integration with SAP Cloud Identity Service](../30-initial-setup/initial-setup-8347694.md#loio834769400794464489f390350a82bbd6__CIS).

The task may have been assigned an ID, which is internal to the task provider/ task-provider specific. In this case, it will appear in cache but will not be assigned to the correct processor.



### 2. Check if the task type is supported.

Check if the task type is supported by SAP Task Center. For more information, see [Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md).



### 3. Check for `tc.enabled` property.

Check in the task provider destination if the `tc.enabled` property is set to `true`.

For more information on the destinations to task providers, see [Destinations to Task Providers](../40-administration/destinations-to-task-providers-b158111.md).



### 4. Check when the task was crated and updated.

SAP Task Center loads the tasks, which have been updated or created in the past 90 days. Previous tasks are not loaded into SAP Task Center.



### 5. Check the Task Center Administration app.

Open the *Connectors* tab in the [Task Center Administration App](../40-administration/monitoring-9b30be7.md#loio9b30be76f14f48c5a72dd7ed7e9babe0__section_AdminApp). Find the connector to the task provider where you expect the task to be created. Check if *INITIAL* pull load of this task provider has completed.



### 6. If the *INITIAL* pull job has not passed.

Wait for the *INITIAL* pull job to pass. If it doesn't pull the tasks correctly, then check the error message it returns and analyze it.



### 7. If the *INITIAL* pull has passed, check *PUSH*/ *DELTA*.

Depending on the setup of your task provider destination, you need to check the *DELTA* or *PUSH* job as follows:

-   If no push is set up for the task provider destination, and the *INITIAL* job has passed, then check the *DELTA* job.

-   If a push mechanism is enabled for the task provider, and the *INITIAL* job has passed, check the status of the *PUSH* job.

    In case there is a *PUSH* enabled for the task provider, the *DELTA* job is paused.


Open the [Task Center Administration App](../40-administration/monitoring-9b30be7.md#loio9b30be76f14f48c5a72dd7ed7e9babe0__section_AdminApp) \>*Connectors*, search for the task provider, and choose the *DELTA*/ *PUSH* job.



### 8. The status of the *DELTA*/ *PUSH* job is in error.

In the Task Center Administration app, check the error message of the *DELTA*/ *PUSH* job and analyze it.



### 9. The status of the *DELTA*/ *PUSH* job is *OK*.

If the status is *OK*, check the messages in the *Logs* view for the number of tasks stored in the cache.

Possible outcomes:

-   If "Stored tasks in CACHE: 0"/ "Received Tasks", the task has not been created.

-   At least one task in the task cache.

To investigate the possible reasons, follow the next step and create a new task.



### 10. Create a new test task.

Create a new test task for the same task provider, making sure that you can distinguish this task among others in a task list. Please, take screenshots with a timestamp when creating the new task, as they might be needed for further troubleshooting.



### 11. If the tasks in cache show 0. 

Refresh the Task Center Administration app in a few minutes and check again the number of tasks for the same task provider in the task cache. 

If there are no tasks stored in cache, it may mean that the task hasn't been created. Please, wait for a couple of minutes for the task to arrive. If you still don't get the task, open a ticket to the task provider component.

For more information on the support components, see SAP Note [3044195 - SAP Task Center Support Components](https://me.sap.com/notes/3044195/E).



### 12. If there is at least one task in the task cache.

If the number of tasks in the task cache has grown, search for the newly created test task in the SAP Task Center Web app task list.



### 13. The new task is received in the task cache.

If the number of tasks stored in the task cache in the Task Center Administration app has grown, these are the possible outcomes:

-   The task is received by SAP Task Center without errors. Check for the test task in the Web app.
-   The task is received in error state.



### 14. The task is received with an error.

If the task was received in the task cache \(you've identified that the number of tasks has grown\), but there is an error in the *Logs* view, depending on the error, create a ticket to the task provider, describing all the steps you've taken so far and include as much detail as possible with screenshots.

For more information on the support components, see SAP Note [3044195 - SAP Task Center Support Components](https://me.sap.com/notes/3044195/E).



### 15. If you can't identify the new task in the task list, or the task does not appear in the list.

If there are too many tasks in your task list and you can't easily find the newly created task, use the [Export SAP Task Center Service Data](../40-administration/export-sap-task-center-service-data-1dfb750.md) \(or [API Data Export](https://api.sap.com/api/TaskCenterAPIForCloudFoundry/resource/Data_Export)\) to export data for the task provider.

To do this, go to *API Business Hub* \> *SAP Task Center API* \> *API Reference*.

To export the data only for the specific task provider, specify the parameter `conectorId` with `value=Connector ID`. The exported `.zip` file contains the following files:

-   `readme.txt`;
-   `tasks.json` – cache tasks;
-   `task-users.json`– contains the mapping between the tasks \(`urn:` from `tasks.json` file\) and the user \(`principalId`\) this task was assigned to.

Search for the newly created test task in the `tasks.json` file. First, open *Tasks* and look for the task by title/ ID/ subject.

If you can find the task in the task cache, it means that it was received by SAP Task Center.

If you cannot find the task in the task list:

-   It was not provided by the task provider; or
-   There was an error while persisting the task.



### 16. After the export the task was not there.

If you didn't find the task in cache after export, it means it’s not been stored. Either the task provider has not sent it, or there was an error. In this case, open a ticket with screenshots and as much detail as possible to the SAP Task Center service.

For more information on the support components, see SAP Note [3044195 - SAP Task Center Support Components](https://me.sap.com/notes/3044195/E).



### 17. After the export the task was there.

In the `tasks.json` file, check the `isValid` property of the task. This property verifies if all requisites are present.



### 18. The `isValid` property is `false`.

If the `isValid` property is `false`, the task won’t appear in the Web app because at least one of the mandatory elements is missing. 

In this case, open a ticket with screenshots and as much detail as possible to the SAP Task Center service.

> ### Tip:  
> Have in mind that some providers trigger multiple partial pushes of the same task because different task properties change sequentially at the task provider side. Therefore, the `isValid` property may be `false` for some time. After several partial pushes all the required properties may appear and the `isValid` property will be set to `true`.



### 19. The `isValid` property is `true`.

If the `isValid` property is `true`, check for the `processor` property. Every task must have an assigned processor, and the ID of the processor must be the global user ID of the respective person in SAP Cloud Identity Services. For more information, see [Integrate with SAP Cloud Identity Services](../30-initial-setup/initial-setup-8347694.md) and [Global User ID in Integration Scenarios](https://help.sap.com/docs/cloud-identity/system-integration-guide/global-user-id-in-integration-scenarios?version=Cloud).



### 20. There is a task processor.

Verify in the Identity Authentication service if the value of the `processor` property corresponds to the global user ID of the correct user.

Possible outcomes:

-   The value of `processor` does not correspond to the correct user or it has a wrong format.

    In this case, open a ticket with screenshots and as much detail as possible to the SAP Task Center service. Please, also send network traces.

-   The value of `processor` corresponds to the correct user but you cannot find the task in the Web app.

    In this case, open a ticket to the task provider. For more information on the support components, see SAP Note [3044195- SAP Task Center Support Components](https://me.sap.com/notes/3044195/E).




### 21. There is no processor, or the processor is not the correct person.

If there’s no processor, or the processor is not the correct user, proceed as follows:

1.  Copy the value of the `instanceID` from the `tasks.json` file.
2.  Open `taskusers.json` and search for this `instanceID` value.
3.  When you find the `instanceID`, make sure that it is assigned to the `principalId`, which corresponds to the global user ID of the correct user.

If in the `taskusers.json` there is no record with an `instanceId` \(the `urn` of the task you're troubleshooting\) and a `principalId` \(the global user ID of the user who is expected to see the task\), the task has not been properly assigned to the user.



### 22. There is no user ID.

In case the task is there but there's no user ID, there are two possibilities:

-   The task has no `principalID`.
-   The `principalID` has an unconventional format \(for example, an email\).

In both cases, open a ticket to the task provider. For more information on the support components, see SAP Note [3044195- SAP Task Center Support Components](https://me.sap.com/notes/3044195/E).



### 23. The task was assigned to a group of users.

If a task is assigned to an Identity Authentication user group, make sure that:

1.  This group exists in the Identity Authentication service.
2.  The user is part of this group.

To verify, check `taskusers.json` record `principaltype: Group`.

If a group assignment is found:

1.  Verify that this group exists in the Identity Authentication service. If it doesn't, create a ticket to the task provider. Task assignments must only use Identity Authentication service groups.

2.  Verify that the user is a member of the Identity Authentication service group. If they're not a member of the group, contact your administrator and ask to add the user to the respective Identity Authentication group.


If neither of these options resolves the issue, open a ticket to the SAP Task Center service with a description of all the steps taken.

> ### Note:  
> For more information on the support components, see SAP Note [3044195 - SAP Task Center Support Components](https://me.sap.com/notes/3044195/E).
> 
> When submitting the incident, please include the following information:
> 
> -   Landscape information \(for example, EU10, US10\).
> 
> -   The URL of the page where the incident or error occurs.
> 
> -   Your tenant ID or subaccount ID.
> 
> -   The steps or clicks used to replicate the error.
> 
> -   Screenshots, videos, or the code entered.
> 
> 
> Please mention also your task providers, details about your authorization method, and links to the documentation you have followed.
> 
> Use the [Export SAP Task Center Service Data](../40-administration/export-sap-task-center-service-data-1dfb750.md) \(or [API Data Export](https://api.sap.com/api/TaskCenterAPIForCloudFoundry/resource/Data_Export)\) to export data for the task provider and attach it to the ticket.

**Related Information**  


[Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md "The Task Center Administration app displays the status of SAP Task Center service, status of all active destinations, and information about their jobs and job types.")

[Conventions and Technical Restrictions](../10-what-is/conventions-and-technical-restrictions-f0f13bf.md "These conventions and restrictions apply to the SAP Task Center.")

[Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md "Review the list of the supported solutions and use cases in SAP Task Center.")

[Initial Setup](../30-initial-setup/initial-setup-8347694.md "To use the service, make sure you have performed the preliminary setup and meet the prerequisites. Then continue with the initial setup for SAP Task Center, following either the automatic setup (using a booster) or the manual setup.")

[Destinations](../40-administration/destinations-3470733.md "SAP Task Center communicates with the task provider applications via predefined destinations in a customer subaccount.")

