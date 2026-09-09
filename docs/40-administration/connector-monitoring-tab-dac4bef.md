<!-- loiodac4bef918094d22b6f6aa7a5e5200cf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Connector Monitoring Tab

Use the *Connector Monitoring* tab to track the status of your connectors, to troubleshoot through detailed messages and event logs, and to export data about specific connectors.



## Using the *Connector Monitoring* Tab

The *Connector Monitoring* tab contains the following views:

-   Connectors View
-   Job View
-   Log View

Initially, you get information only about the active destinations of the connectors. More details are provided when you select one of the connectors and a job type.

The information in the views is provided by the Task Center API. For more information about the Task Center API, see [Using the SAP Task Center API](using-the-sap-task-center-api-b66e0cd.md).



## Connectors View

Information provided in the view:

-   All active connectors to task providers
-   ID of the connector
-   Status of the connector
    -   *OK* – all jobs are in *OK* state

    -   *WARNING* – at least 1 job is in *Warning* state

    -   *ERROR* – at least 1 job is in *Error* state

    -   *PAUSED* – the *tc.enabled* property of the connector is set to `false` 



Use the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Connectors* button at the top of the table to refresh the connectors. You can also refresh individual task providers by using the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span>*Cache* button in the table. The Job and Log view are also refreshed if they are open.

Refreshing the task cache deletes the tasks of the chosen task provider and repopulates it with tasks from the past up to 180 days, which corresponds to the set maximum initial pull period.

For more information about the maximum initial pull period, see. [Conventions and Technical Restrictions](../10-what-is/conventions-and-technical-restrictions-f0f13bf.md).

For more information about repopulating the task cache, see [Repopulate the Task Cache](repopulate-the-task-cache-e93aa71.md).

> ### Caution:  
> Refreshing the task cache can be a high-load operation. You can only refresh the task cache of up to 2 of your task providers simultaneously.

Use the *Export Cache* button to export data about a specific task provider. For more information, see [Export SAP Task Center Service Data](export-sap-task-center-service-data-1dfb750.md).

Related end point: `/task-center-service/v1/connectors`



## Job View

Information provided in the view:

-   Status of the selected connector
-   All available job types for the selected connector
    -   *INITIAL* 
    -   *CONFIG* 
    -   *DELTA* 
    -   *META* 
    -   *PUSH* 

-   Statuses of the job types:
    -   *OK* 
    -   *RUNNING* 
    -   *WARNING* 
    -   *ERROR* 

-   More details about the job type

Use the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Job Status* button to refresh all jobs. The Log view is also refreshed if it is opened.

For more information about the available job types and their statuses, see [Monitoring](monitoring-9b30be7.md).

Related end point: `/task-center-service/v1/connectors/{connectorId}`



## Log View

Information provided in the view:

-   Job status and job type
-   All log messages, start, and end of the log

Use the <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Event Log* button to refresh the events.

Related end point: `/task-center-service/v1/connectors/{connectorId}/jobTypes/{jobType}`

