<!-- loio3a1598cb4b774536befb701f78b36e48 -->

# Working with the Task Center Administration App

The Task Center Administration app displays the status of all active destinations, information about their jobs and job types.



The Task Center Administration app connects to the SAP Task Center Connector Status API and helps administrators monitor the overall status of all configured destination connectors, configured on the account of the SAP Task Center instance.

For more information about the Connector Status API, see [SAP API Business Hub Task Center API](https://int.api.hana.ondemand.com/package/SAPTaskCenter?section=Artifacts).

For more information about the languages supported in the Task Center Administration app, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).



<a name="loio3a1598cb4b774536befb701f78b36e48__section_nsx_wmx_sqb"/>

## Prerequisites

-   You have created a Task Center Administration tile. For more information, see [Create a Task Center Administration Tile on SAP Build Work Zone, Standard Edition](../30-initial-setup/create-a-task-center-administration-tile-on-sap-build-work-zone-standard-edition-55fc2c0.md).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loio3a1598cb4b774536befb701f78b36e48__section_k2t_tkf_mqb"/>

## Working with the Task Center Administration App

The Task Center Administration app consists of the following views:

-   Connector View
-   Job View
-   Log View

Initially, you see only the available destinations of the connectors. More details are displayed when you select one of the destinations and a job type.

The information displayed in the views is provided by the Task Center API. For more information about the Task Center API, see [Using the SAP Task Center API](../50-development/using-the-sap-task-center-api-b66e0cd.md).

**Views, Information and Related End Points**


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

Connector View



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
-   All log messages, start and end of the log



</td>
<td valign="top">

`/task-center-service/v1/connectors/{connectorId}/jobTypes/{jobType}`



</td>
</tr>
</table>

**Related Information**  


[Create a Task Center Administration Tile on SAP Build Work Zone, Standard Edition](../30-initial-setup/create-a-task-center-administration-tile-on-sap-build-work-zone-standard-edition-55fc2c0.md "Create a Task Center Administration tile in the SAP Build Work Zone, standard edition (formerly known as SAP Launchpad service) to monitor the status of all active destinations and get information about their jobs and job types.")

[Monitoring](monitoring-9b30be7.md "Once you create a destination configuration to connect SAP Task Center to a task provider application, SAP Task Center creates a connector internally for this configuration.")

[Using the SAP Task Center API](../50-development/using-the-sap-task-center-api-b66e0cd.md "The SAP Task Center API for the Cloud Foundry environment allows you to list and work with user tasks and task definitions, monitor connector configurations, and export service data.")

[SAP Business API Hub documentation](https://api.sap.com/package/SAPTaskCenter?section=Artifacts)

