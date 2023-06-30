<!-- loio3a1598cb4b774536befb701f78b36e48 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with the Task Center Administration App

The Task Center Administration app displays the status of SAP Task Center service, status of all active destinations, and information about their jobs and job types.



The Task Center Administration app connects to the SAP Task Center Monitoring API and helps administrators monitor the overall status of the SAP Task Center service and all destination connectors, configured on the account of the SAP Task Center instance.

For more information about the Monitoring Status API, see [SAP Business Accelerator Hub Task Center API](https://int.api.hana.ondemand.com/package/SAPTaskCenter?section=Artifacts).

For more information about the languages supported in the Task Center Administration app, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).



<a name="loio3a1598cb4b774536befb701f78b36e48__section_nsx_wmx_sqb"/>

## Prerequisites

-   You have created a Task Center Administration tile. For more information, see [Create a Task Center Administration Tile](../30-initial-setup/create-a-task-center-administration-tile-8053d72.md).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loio3a1598cb4b774536befb701f78b36e48__section_k2t_tkf_mqb"/>

## Working with the Task Center Administration App

The Task Center Administration app provides information on the following two tabs:

-   *Connectors*

-   *Service Status*


The *Connectors* tab contains the following views:

-   Destinations View
-   Job View
-   Log View

Initially, you see only the active destinations of the connectors. More details are displayed when you select one of the destinations and a job type.

The information displayed in the views is provided by the Task Center API. For more information about the Task Center API, see [Using the SAP Task Center API](../50-development/using-the-sap-task-center-api-b66e0cd.md).

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

    -   *OK*
    -   *WARNING*
    -   *ERROR*




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



</td>
<td valign="top">

`/task-center-service/v1/connectors/{connectorId}/jobTypes/{jobType}`



</td>
</tr>
</table>

The *Service Status* tab displays the current status of the following destinations:

-   *Task\_Center\_global\_settings*
-   *Identity\_Authentication\_Connectivity\_IDS*

The related end point in the API is `/task-center-service/v1/service-status`.

Use the *Refresh* button \(<span style="color:#346187;"><span class="SAP-icons"></span></span>\) to get the latest status.

> ### Note:  
> The IDs and all messages returned by the SAP Task Center service are only in English.

**Information in the Service Status Table**


<table>
<tr>
<th valign="top">

Column



</th>
<th valign="top">

Details



</th>
</tr>
<tr>
<td valign="top" rowspan="2">

*ID*



</td>
<td valign="top">

The *Service\_Configuration* ID is related to the *Task\_Center\_global\_settings* destination. See also [SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md).



</td>
</tr>
<tr>
<td valign="top">

The *IDS\_Configuration* ID is related to the *Identity\_Authentication\_Connectivity\_IDS* destination. See also [Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md).



</td>
</tr>
<tr>
<td valign="top">

*Status*



</td>
<td valign="top">

The service can have the following status:

-   *OK*
-   *WARNING*
-   *ERROR*

For more information, see the message.

> ### Note:  
> Only the last retrieved status is displayed.



</td>
</tr>
<tr>
<td valign="top">

*Message*



</td>
<td valign="top">

Displays a message returned by the service.



</td>
</tr>
<tr>
<td valign="top">

*Modified At*



</td>
<td valign="top">

Date and time when the last status update was retrieved.



</td>
</tr>
</table>

**Related Information**  


[Create a Task Center Administration Tile](../30-initial-setup/create-a-task-center-administration-tile-8053d72.md "Create a Task Center Administration tile by folloing the links below.")

[Monitoring](monitoring-9b30be7.md "Once you create a destination configuration to connect SAP Task Center to a task provider application, SAP Task Center creates a connector internally for this configuration.")

[Using the SAP Task Center API](../50-development/using-the-sap-task-center-api-b66e0cd.md "The SAP Task Center API for the Cloud Foundry environment allows you to list and work with user tasks and task definitions, monitor connector configurations, and export service data.")

[SAP Business API Hub documentation](https://api.sap.com/package/SAPTaskCenter?section=Artifacts)

[SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md "Configure the Task_Center_global_settings destination, to set the properties valid for all destinations.")

[Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md "Configure the Identity_Authentication_Connectivity_IDS destination to connect to the identity directory of Identity Authentication and retrieve the required information about the end users.")

