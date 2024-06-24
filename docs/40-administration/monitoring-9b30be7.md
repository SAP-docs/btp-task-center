<!-- loio9b30be76f14f48c5a72dd7ed7e9babe0 -->

# Monitoring

Once you create a destination configuration to connect SAP Task Center to a task provider application, SAP Task Center creates a connector internally for this configuration.



For this new configuration, SAP Task Center creates the following background connector job types:

-   *INITIAL* is the initial pull job. It runs for newly created connector destinations and retrieves all tasks, created or updated in the past days, corresponding to the maximum initial pull period, for the specified connector. One connector status record is saved in the status history of this job type. For more information about the maximum initial pull period, see [Conventions and Technical Restrictions](../10-what-is/conventions-and-technical-restrictions-f0f13bf.md).
-   *CONFIG* is a connector configuration job. It is used to adapt to changes of connector destination properties. It pulls the configured destinations every minute and saves a history of the last 10 connector status records.
-   *DELTA* is a delta pull job. It retrieves the latest task updates every 30 seconds. It saves a history of the last 30 connector status records.
-   *META* is a meta data pull job. It retrieves the task definitions once a day. It saves a history of the last 5 connector status records.
-   *PUSH* is a job, which retrieves the latest task updates pushed to SAP Task Center every 5 seconds. It saves a history if the last 30 connector status records.

Each background job can have the following statuses: *OK*, *WARNING*, *RUNNING*, or *ERROR*.



<a name="loio9b30be76f14f48c5a72dd7ed7e9babe0__section_AdminApp"/>

## Task Center Administration App

To monitor the status of the SAP Task Center service and all active destinations, and get information about their jobs and job types, we recommend you to use the Task Center Administration app. It connects to the SAP Task Center Monitoring API and helps administrators monitor the overall status of all destination connectors, configured on the account of the SAP Task Center instance.

For more information, see [Working with the Task Center Administration App](working-with-the-task-center-administration-app-3a1598c.md).



<a name="loio9b30be76f14f48c5a72dd7ed7e9babe0__section_ConnectorStatusAPI"/>

## Connector Status API

SAP Task Center exposes a *Connector Status API* that allows you to monitor:

-   The overall status of all configured destination connector configurations for an SAP Task Center instance
-   The connector jobs for each configured connector
-   A short history of connector job statuses for a connector job of a connector configuration

For more information about accessing the *Connector Status API*, see:

-   [Access the SAP Task Center API Using OAuth 2.0 Authentication \(Authorization Code Grant\)](access-the-sap-task-center-api-using-oauth-2-0-authentication-authorization-code-grant-29928a7.md)
-   [Using the SAP Task Center API](using-the-sap-task-center-api-b66e0cd.md)
-   [Task Center API](https://api.sap.com/package/SAPTaskCenter/rest)



<a name="loio9b30be76f14f48c5a72dd7ed7e9babe0__section_ServiceStatusAPI"/>

## Service Status API

SAP Task Center exposes a *Service Status API* that allows you to monitor:

-   The current configuration status of the *SAP Task Center Global Settings* destination \(see `"code": "Service_Configuration"` in the *Service Status API*\)

-   The current status of the connectivity and configuration of the *Identity Directory Connectivity* destination \(see `"code": "IDS_Configuration"` in the *Service Status API*\)


For more information about accessing the *Service Status API*, see [Task Center API](https://api.sap.com/package/SAPTaskCenter/rest).



<a name="loio9b30be76f14f48c5a72dd7ed7e9babe0__section_IntegrationWithAlert"/>

## Integration with SAP Alert Notification service for SAP BTP

You can set up SAP Alert Notification service for SAP BTP to send notifications for changes in the SAP Task Center background job statuses. For more information, see [Set Up Notifications for Administrators](set-up-notifications-for-administrators-2c1997b.md).

**Related Information**  


[SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md "Configure the Task_Center_global_settings destination, to set the properties valid for all destinations.")

[Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md "Configure the Identity_Authentication_Connectivity_IDS destination to connect to the identity directory of Identity Authentication and retrieve the required information about the end users.")

[Working with the Task Center Administration App](working-with-the-task-center-administration-app-3a1598c.md "The Task Center Administration app displays the status of SAP Task Center service, status of all active destinations, and information about their jobs and job types.")

[Set Up Notifications for Administrators](set-up-notifications-for-administrators-2c1997b.md "You can set up the SAP Alert Notification service for SAP BTP to send notifications for changes in the SAP Task Center background job statuses.")

[Integration with SAP Cloud ALM](integration-with-sap-cloud-alm-092288d.md "Use the integration of SAP Task Center with SAP Cloud ALM (application lifecycle management) to monitor all the inbound and outbound communication data events with the SAP Task Center REST API. This information pertains to events that a customer system administrator needs to know in order to resolve critical issues, related to task management events.")

