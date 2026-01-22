<!-- loio3a1598cb4b774536befb701f78b36e48 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with the Task Center Administration App

The Task Center Administration app provides an overview of the SAP Task Center service status, the status of all active destinations, including information about their jobs and job types. It allows configuration of the SAP Task Center global settings.



The Task Center Administration app connects to the SAP Task Center Monitoring API and helps administrators monitor the overall status of the SAP Task Center service and all destination connectors, configured on the account of the SAP Task Center instance.

In the Task Center Administration app you can also set the global settings of SAP Task Center that apply to all task providers.

For more information about the Monitoring Status API, see [SAP Business Accelerator Hub Task Center API ](https://int.api.hana.ondemand.com/package/SAPTaskCenter?section=Artifacts).

For more information about the languages supported in the Task Center Administration app, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).



<a name="loio3a1598cb4b774536befb701f78b36e48__section_nsx_wmx_sqb"/>

## Prerequisites

-   You have created a Task Center Administration tile. For more information, see [Create a Task Center Administration Tile](../30-initial-setup/create-a-task-center-administration-tile-8053d72.md).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loio3a1598cb4b774536befb701f78b36e48__section_k2t_tkf_mqb"/>

## Working with the Task Center Administration App

The Task Center Administration app provides information on the following tabs:

-   *Connectors* 

-   *Service Status* 

-   *Global Settings* 



### Connectors Tab

The *Connectors* tab contains the following views:

-   Destinations View
-   Job View
-   Log View

Initially, you get information only about the active destinations of the connectors. More details are provided when you select one of the destinations and a job type.

The information in the views is provided by the Task Center API. For more information about the Task Center API, see [Using the SAP Task Center API](using-the-sap-task-center-api-b66e0cd.md).

Use the *Export Cache* button to export data about a specific destination. For more information, see [Export SAP Task Center Service Data](export-sap-task-center-service-data-1dfb750.md).

**Views, Information, and Related End Points**


<table>
<tr>
<th valign="top">

View

</th>
<th valign="top">

Information Provided in the View

</th>
<th valign="top">

Related End Point

</th>
</tr>
<tr>
<td valign="top">

Destinations View

</td>
<td valign="top">

-   All active destinations
-   ID of the destination
-   Status of the destination

    The destinations can have one of the following statuses:

    -   *OK* – all jobs are in *OK* state

    -   *WARNING* – at least 1 job is in *Warning* state

    -   *ERROR* – at least 1 job is in *Error* state

    -   *PAUSED* – the *tc.enabled* property of the destination is set to `false` 



Use the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Connectors* button to refresh the destinations. The Job and Log view are also refreshed if they are opened.

</td>
<td valign="top">

`/task-center-service/v1/connectors` 

</td>
</tr>
<tr>
<td valign="top">

Job View

</td>
<td valign="top">

-   Destination status of the selected destination
-   All available job types for the selected destination

    The job types can be:

    -   *INITIAL* 
    -   *CONFIG* 
    -   *DELTA* 
    -   *META* 
    -   *PUSH* 

-   Statuses of the job types

    The jobs can have one of the following statuses:

    -   *OK* 
    -   *RUNNING* 
    -   *WARNING* 
    -   *ERROR* 

-   More details about the job type

Use the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Job Status* button to refresh all jobs. The Log view is also refreshed if it is opened.

For more information about the available job types and their statuses, see [Monitoring](monitoring-9b30be7.md).

</td>
<td valign="top">

`/task-center-service/v1/connectors/{connectorId}` 

</td>
</tr>
<tr>
<td valign="top">

Log View

</td>
<td valign="top">

-   Job status and job type
-   All log messages, start, and end of the log

Use the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Event Log* button to refresh the events.

</td>
<td valign="top">

`/task-center-service/v1/connectors/{connectorId}/jobTypes/{jobType}` 

</td>
</tr>
</table>



### Service Status Tab

The *Service Status* tab provides information about the current status of the following destinations:

-   *Task\_Center\_global\_settings* 
-   *Identity\_Authentication\_Connectivity\_IDS* 

The related end point in the API is `/task-center-service/v1/service-status`.

Use the *Refresh* button \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) to get the latest status.

> ### Note:  
> The IDs and all messages returned by the SAP Task Center service are only in English.
> 
> **Information in the Service Status Table**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Column
> 
> </th>
> <th valign="top">
> 
> Details
> 
> </th>
> </tr>
> <tr>
> <td valign="top" rowspan="2">
> 
> *ID* 
> 
> </td>
> <td valign="top">
> 
> The *Service\_Configuration* ID is related to the *Task\_Center\_global\_settings* destination. See also [SAP Task Center Global Settings](../30-initial-setup/sap-task-center-global-settings-99e5302.md).
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> The *IDS\_Configuration* ID is related to the *Identity\_Authentication\_Connectivity\_IDS* destination. See also [Identity Directory Connectivity](../30-initial-setup/identity-directory-connectivity-3dcfba9.md).
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> *Status* 
> 
> </td>
> <td valign="top">
> 
> The service can have the following status:
> 
> -   *OK* 
> -   *WARNING* 
> -   *ERROR* 
> 
> For more information, see the message.
> 
> > ### Note:  
> > Only the last retrieved status is displayed.
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> *Message* 
> 
> </td>
> <td valign="top">
> 
> Displays a message returned by the service.
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> *Modified At* 
> 
> </td>
> <td valign="top">
> 
> Date and time when the last status update was retrieved.
> 
> </td>
> </tr>
> </table>



### Global Settings Tab

The *Global Settings* tab provides the following information about the settings in SAP Task Center that are valid for all task providers:

-   *Languages* - allows you to pick up to 3 languages for the translations of tasks and task definitions. For more information, see [Technical Restrictions](../10-what-is/conventions-and-technical-restrictions-f0f13bf.md#loiof0f13bf49e3f45488bcf24218a2771e4__section_q4p_zk5_ymb).
-   *Outbox* - allows you to enable or disable the *Outbox* tab in the Web app which shows completed tasks. For more information, see [SAP Task Center Global Settings](../30-initial-setup/sap-task-center-global-settings-99e5302.md).
-   *Email Notifications Root URL* - allows you to set the root URL that is used for generating working links in email notifications. For more information, see [Enable Notifications for End Users](enable-notifications-for-end-users-caf2543.md).

> ### Note:  
> To use the *Global Settings* tab, you must first create the *Task\_Center\_global\_settings* destination. This destination can't be created through the SAP Task Center Administration app.

Any changes you make in the *Global Settings* tab are automatically synchronized with the destination and vice versa. Keep in mind that

For more information on each setting, see [SAP Task Center Global Settings](../30-initial-setup/sap-task-center-global-settings-99e5302.md).



<a name="loio3a1598cb4b774536befb701f78b36e48__section_tmy_ww5_xbc"/>

## Intelligent Recommendations

On the *Intelligent Recommendations* tab you can create AI models to propose recommendations for the end users. These recommendations are based on the confidence level generated for the task. The confidence level is a numerical value ranging from 0 to 100, which is calculated by a trained AI model. A higher confidence level encourages positive action on the task, such as approval.

Before you start creating intelligent recommendation models, make sure you have configured the destination required for this feature. For more information, see [Configure the Intelligent Recommendations Destination](../configure-the-intelligent-recommendations-destination-7c8900a.md).

For more information on how to start creating intelligent recommendation models, see [Working with Intelligent Recommendations](working-with-intelligent-recommendations-340651c.md).



<a name="loio3a1598cb4b774536befb701f78b36e48__section_ahw_yw5_xbc"/>

## Substitution Management

On the *Substitution Management* tab business administrators can create substitution rules on behalf of end users, or manage existing substitution rules.

For more information, see [Using Substitution Management for Business Administrators](using-substitution-management-for-business-administrators-3adfedc.md).

**Related Information**  


[Create a Task Center Administration Tile](../30-initial-setup/create-a-task-center-administration-tile-8053d72.md "Create a Task Center Administration tile in the central point of entry for accessing applications of your choice, to provide the opportunity to administrators to monitor the status of the SAP Task Center service and all active destinations, and get information about their jobs and job types.")

[Monitoring](monitoring-9b30be7.md "Once you create a destination configuration to connect SAP Task Center to a task provider application, SAP Task Center creates a connector internally for this configuration.")

[Using the SAP Task Center API](using-the-sap-task-center-api-b66e0cd.md "The SAP Task Center API allows you to list and work with user tasks and task definitions, monitor connector configurations, and export service data.")

[SAP Business API Hub documentation](https://api.sap.com/package/SAPTaskCenter?section=Artifacts)

[SAP Task Center Global Settings](../30-initial-setup/sap-task-center-global-settings-99e5302.md "Configure the Task_Center_global_settings destination, to set the properties valid for all destinations.")

[Identity Directory Connectivity](../30-initial-setup/identity-directory-connectivity-3dcfba9.md "Configure the Identity_Authentication_Connectivity_IDS destination to connect to the identity directory of Identity Authentication and retrieve the required information about the end users.")

[Working with Intelligent Recommendations](working-with-intelligent-recommendations-340651c.md "You can create intelligent recommendation model to manage recommedations for the approval tasks.")

[Using Substitution Management for Business Administrators](using-substitution-management-for-business-administrators-3adfedc.md "As a business administrator you can search by users and manage their existing substitution rules.")

