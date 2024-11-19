<!-- loio1bcdd459f84d4323a27581226d1d210e -->

# What's New for SAP Task Center





**2024**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Environment

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Lifecycle

</th>
<th valign="top">

Type

</th>
<th valign="top">

Line of Business

</th>
<th valign="top">

Modular Business Process

</th>
<th valign="top">

Product

</th>
<th valign="top">

Latest Revision

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New Properties to Optimize Search Performance

</td>
<td valign="top">

Two new properties *tc.pp.user\_types* and *tc.pp.search\_operation* can be set up to optimize the performance of the people search engine for very large user groups.

For more information, see [Identity Directory Connectivity](../40-administration/identity-directory-connectivity-3dcfba9.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-11-19

</td>
<td valign="top">

2024-11-19

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Troubleshooting Guide Extended

</td>
<td valign="top">

The troubleshooting guide for administrators is extended with details on how to troubleshoot missing tasks.

For more information, see [Troubleshooting a Task at SAP Task Center \(For Administrators\)](../80-troubleshooting/troubleshooting-a-task-at-sap-task-center-for-administrators-2f26551.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-11-05

</td>
<td valign="top">

2024-11-05

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Task Recipients Limited to 100

</td>
<td valign="top">

Please note that the task recipients are restricted by SAP Task Center to 100 members, applicable to both users and user groups.

For more information, see [Conventions and Technical Restrictions](../10-what-is/conventions-and-technical-restrictions-f0f13bf.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-11-05

</td>
<td valign="top">

2024-11-05

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

SAP Task Center Improvements

</td>
<td valign="top">

The following improvements are introduced for the SAP Task Center Web app:

-   Handling of attachments with IDs that include special characters

-   Support for opening task directly via deep links




</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-28

</td>
<td valign="top">

2024-10-28

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

*Claim*, *Release*, and *Forward* Now Available for SAP Build Process Automation Tasks

</td>
<td valign="top">

*Claim*, *Release*, and *Forward* can now be performed, and are available as inline actions on SAP Build Process Automation tasks. For more information on the supported features, see [Supported Features](../10-what-is/supported-features-257a0ad.md).

Additional configuration is required for the cases when SAP Build Process Automation and SAP Task Center are in different subaccounts. For more information, see SAP Note [3522594](https://me.sap.com/notes/3522594).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-17

</td>
<td valign="top">

2024-10-17

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Additional Property Required for SAP Build Process Automation 

</td>
<td valign="top">

If you are:

-   using SAP Build Process Automation as task provider,

-   SAP Build Process Automation and SAP Task Center are in different subaccounts,

-   the established trust with Identity Authentication is SAML 2.0 \(see [Establish Trust with Identity Authentication](https://help.sap.com/docs/build-process-automation/sap-build-process-automation/establish-trust-with-identity-authentication-43d62657284f4505b2d75f000210bf82?version=Cloud)\),


then make sure you add the *wfs.tc.sec.prot.rel* property in your SAP Build Process Automation`Identity_Authentication_Connectivity_IDS` destination and set its value to `true`.

For more information, see SAP Note [3522594](https://me.sap.com/notes/3522594).

> ### Note:  
> -   If you don’t set this property, the end users might be able to access their SAP Build Process Automation tasks, but some actions might not be available in the Web app.
> 
> -   If you have already set up the property `wfs.tc.local`, please remove it from your SAP Build Process Automation `Identity_Authentication_Connectivity_IDS` destination, regardless of whether your SAP Build Process Automation and SAP Task Center are in the same or different subaccounts.



</td>
<td valign="top">

Required

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-17

</td>
<td valign="top">

2024-10-17

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

UiPath Supported as Task Provider

</td>
<td valign="top">

You can now connect UiPath as task provider to SAP Task Center. For more information, see [Connect UiPath and SAP Task Center](../40-administration/connect-uipath-and-sap-task-center-223b083.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-15

</td>
<td valign="top">

2024-10-15

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

No Additional Subscriptions for Central Point of Entry for Accessing Applications Are Required for SAP Build Process Automation Tasks

</td>
<td valign="top">

A new property `tc.task.ui.url` allows you to access tasks without the need of an additional central point of entry for accessing application for SAP Build Process Automation.

For more information, see [Work with SAP Build Process Automation Tasks from the Same Subaccount](../40-administration/work-with-sap-build-process-automation-tasks-from-the-same-subaccount-f9c57ee.md) or [Work with SAP Build Process Automation Tasks from a Different Subaccount](../40-administration/work-with-sap-build-process-automation-tasks-from-a-different-subaccount-1d3e69d.md).

</td>
<td valign="top">

Required

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-15

</td>
<td valign="top">

2024-10-15

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Additional Property Required for SAP Build Process Automation 

</td>
<td valign="top">

If you are using SAP Build Process Automation as task provider, you must set up an additional property in your SAP Build Process Automation `Identity_Authentication_Connectivity_IDS` destination, as follows:

-   If SAP Build Process Automation and SAP Task Center are in the same subaccount, set the `wfs.tc.local` property to `true`.

-   If SAP Build Process Automation and SAP Task Center are in different subaccounts, set the `wfs.tc.local` property to `false`.


For more information, see SAP Note [3522594](https://me.sap.com/notes/3522594).

If you don’t set this property, the end users might be able to access their SAP Build Process Automation tasks, but some actions might not be available in the Web app.

</td>
<td valign="top">

Required

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-02

</td>
<td valign="top">

2024-10-02

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Substitution Management for Business Administrators Enabled in the Task Center Administration App

</td>
<td valign="top">

In the Task Center Administration app business administrators can create substitution rules on behalf of end users, and manage existing substitution rules, created by end users.

For more information, see [Using Substitution Management for Business Administrators](../40-administration/using-substitution-management-for-business-administrators-3adfedc.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-02

</td>
<td valign="top">

2024-10-02

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

SAP Task Center Improvements

</td>
<td valign="top">

Notifications are now displayed consistently for all supported task providers without being deleted every 24 hours.

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-10-02

</td>
<td valign="top">

2024-10-02

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Notifications Via Email Enabled

</td>
<td valign="top">

Administrators can now set up an email server to enable email notifications for end users. For more information on how to set up the email server, see [Enable Notifications for End Users](../40-administration/enable-notifications-for-end-users-caf2543.md).

> ### Note:  
> After administrators have set up the email server, they should inform the end users about the new functionality and how to enable it.



</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-09-16

</td>
<td valign="top">

2024-09-16

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

*Intelligent Recommendations* Feature Available for SAP Build Process Automation Tasks

</td>
<td valign="top">

The new *Intelligent Recommendations* feature is now available for SAP Build Process Automation tasks.

Administrators can now create AI models to offer to the end users a confidence level for their SAP Build Process Automation tasks in the SAP Task Center Web app.

For more information, see [Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md) and [Working with Intelligent Recommendations](../40-administration/working-with-intelligent-recommendations-340651c.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-09-11

</td>
<td valign="top">

2024-09-11

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Enhanced Error Messages and Extended Export API Functionality

</td>
<td valign="top">

We made the following improvements:

-   Enhanced error messages in the SAP Task Center Administration app for easier troubleshooting.

-   Extended Export API to include task definitions in the exported file.




</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-09-02

</td>
<td valign="top">

2024-09-02

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Improvements

</td>
<td valign="top">

The following improvements are made in the SAP Task Center Web app:

-   Attachments and comments related to a task are now persistently displayed when switching between tasks.

-   The *Enter Full-Screen Mode* and *Close Column* buttons are now consistently visible, regardless of screen size.

-   A visual separator has been added between the *Open in App* and the option to enter full-screen mode, making it easier to distinguish and select the desired action.




</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-08-21

</td>
<td valign="top">

2024-08-21

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

SAP Fieldglass `CONFIG` Job Failing

</td>
<td valign="top">

The `CONGIF` job for new or existing destinations to SAP Fieldglass might be failing.

For more information, see SAP Note [3507354](https://me.sap.com/notes/3507354).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-08-15

</td>
<td valign="top">

2024-08-15

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Improvements

</td>
<td valign="top">

The following improvements are made in the SAP Task Center Web app:

-   In the decision options not displayed in native user interface for task details.

-   In the navigation to next task, which has failed when completing a task in the Web app in full-screen mode.




</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-08-15

</td>
<td valign="top">

2024-08-15

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Check and Update Your Service Keys and Bindings

</td>
<td valign="top">

Please make sure your SAP Task Center service keys and service bindings are following the new pattern \(created after July 2022\).

If they are following the old pattern, make sure to recreate and update them by August 31, 2024.

For more information, see SAP Note [3499354](https://me.sap.com/notes/3499354).

</td>
<td valign="top">

Required

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-07-24

</td>
<td valign="top">

2024-07-24

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Improvements

</td>
<td valign="top">

Improvements in the SAP Task Center Web App:

-   Improvements in the translation handling of the attachments and comments area.

-   Improvements in the error handling in the Web app by creating human-readable messages.




</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-07-22

</td>
<td valign="top">

2024-07-22

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Updated Documentation for Creating a Tile

</td>
<td valign="top">

The topics describing how to create the SAP Task Center tiles have now been updated to point to the documentation of the central point of entry for accessing applications. For more information, see [Create a Task Center Tile](../30-initial-setup/create-a-task-center-tile-70e7f6e.md) and [Create a Task Center Administration Tile](../30-initial-setup/create-a-task-center-administration-tile-8053d72.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-07-22

</td>
<td valign="top">

2024-07-22

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New Destination Status in the SAP Task Center Administration App

</td>
<td valign="top">

A new connector status *PAUSED* is introduced in the SAP Task Center Administration app. For more information, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-07-22

</td>
<td valign="top">

2024-07-22

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Minor Improvements

</td>
<td valign="top">

For enhanced performance, the removal of unused API has been finalized.

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-07-09

</td>
<td valign="top">

2024-07-09

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Integration with SAP Cloud ALM

</td>
<td valign="top">

You can now use the integration of SAP Task Center with SAP Cloud ALM to monitor all the inbound and outbound communication data events with the SAP Task Center REST API.

For more information, see [Integration with SAP Cloud ALM](../40-administration/integration-with-sap-cloud-alm-092288d.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-06-24

</td>
<td valign="top">

2024-06-24

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Performance Optimization

</td>
<td valign="top">

Unused APIs have been removed for improved performance and optimization of the SAP Task Center service.

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-06-24

</td>
<td valign="top">

2024-06-24

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Minor Updates

</td>
<td valign="top">

The following improvements have been made:

-   In the communication between the SAP Task Center Web app and the iFrame embedded UI;

-   In the handling of custom attributes, attachment counts and the description shown in the *Additional Information* tab of the standard task UI;

-   In the loading of views with expired filter criteria;

-   In the task count for tasks, processed on behalf of another user;




</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-06-12

</td>
<td valign="top">

2024-06-12

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Third-Party Task Provider Supported

</td>
<td valign="top">

You can now connect a third-party task provider to SAP Task Center. For more information, see [Connect a Third-Party Task Provider and SAP Task Center](../40-administration/connect-a-third-party-task-provider-and-sap-task-center-c6362b6.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-06-05

</td>
<td valign="top">

2024-06-05

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Security Topic Updated

</td>
<td valign="top">

The security information for SAP Task Center is extended with more details about the SAP Cloud Identity Services and third-party integration.

For more information, see [Security](../60-security/security-2ab2142.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-06-05

</td>
<td valign="top">

2024-06-05

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Minor Updates

</td>
<td valign="top">

Performance optimization in the SAP Task Center Web App.

Improvement of the delta job status retention policy to store the status of only the last 30 delta jobs in the database. Applied automatically. No action required.

Improvement in the navigation from a notification to a task that has already been processed.

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-05-28

</td>
<td valign="top">

2024-05-28

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Labels *Claim*, *Release*, *Forward* Are Now Consistent for All Task Providers

</td>
<td valign="top">

The labels for the actions *Claim*, *Release*, and *Forward* are now defined by the SAP Task Center Web app and are consistent for all task providers. For more informaiton, see [Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md) \> [Inline Decision Options and Predefined Decision Reasons](https://help.sap.com/docs/task-center/sap-task-center/working-with-task-list?version=Cloud#inline-decision-options-and-predefined-decision-reasons).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-05-14

</td>
<td valign="top">

2024-05-14

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   


</td>
<td valign="top">

Updated Icons for SAP Concur and SAP Fieldglass 

</td>
<td valign="top">

The icons for SAP Concur and SAP Fieldglass in the filter tabs of the SAP Task Center Web app are now updated. For more information, see [Configure Filter Tabs in the SAP Task Center Web App](../40-administration/configure-filter-tabs-in-the-sap-task-center-web-app-53157da.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-05-14

</td>
<td valign="top">

2024-05-14

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Updating HTML5 Apps Required

</td>
<td valign="top">

Following this week's update of SAP Task Center, it is expected that the *Task Center* tile count will start showing *Error*. To restore the tile count, please update the HTML5 apps in the site manager of your central point of entry for accessing apps. For example, see central point of entry for accessing apps. For example, see [Create a Task Center Tile](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/create-task-center-tile) for SAP Build Work Zone, advanced edition.

. To restore theЕnd users might have to clear browser cache and refresh their browser.

</td>
<td valign="top">

Required

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-04-19

</td>
<td valign="top">

2024-04-19

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Public Views Enabled

</td>
<td valign="top">

You can now access public views, predefined by key users. For more information, see [Working with Views](../70-using-the-web-app/working-with-views-b446cc8.md) and [Creating Public Views for End Users](../40-administration/creating-public-views-for-end-users-4c2c2af.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-04-19

</td>
<td valign="top">

2024-04-19

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Pushing SAP S/4HANA and SAP S/4HANA Cloud, private edition Tasks Enabled

</td>
<td valign="top">

You can now enable task updates to be pushed from SAP S/4HANA or SAP S/4HANA Cloud, private edition. For more information, see the *Prerequisites* section and *tc.clientId* in [Connect SAP S/4HANA and SAP Task Center](../40-administration/connect-sap-s-4hana-and-sap-task-center-143af9b.md) and [Connect SAP S/4HANA Cloud, private edition and SAP Task Center](../40-administration/connect-sap-s-4hana-cloud-private-edition-and-sap-task-center-50ce133.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-03-20

</td>
<td valign="top">

2024-03-20

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Support for New Actions - *Claim*, *Release*, *Forward* 

</td>
<td valign="top">

*Claim*, *Release* and *Forward* are now available for SAP S/4HANA, SAP S/4HANA Cloud, public edition and SAP S/4HANA Cloud, private edition tasks.

For more information, see [Inline Decision Options and Predefined Decision Reasons](https://help.sap.com/docs/task-center/sap-task-center/working-with-task-list?version=Cloud#inline-decision-options-and-predefined-decision-reasons).

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-02-05

</td>
<td valign="top">

2024-02-05

</td>
</tr>
<tr>
<td valign="top">

SAP Task Center 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Restart Notifications

</td>
<td valign="top">

A change in the setup of the notifications has been introduced and requires your action.

If you have already set up notifications for SAP Task Center, please set the *tc.notifications.enabled* property from every task provider destination to `false`, wait for a few minutes and set it back to `true`.

For more information on the task provider destinations, see [Destinations](../40-administration/destinations-3470733.md).

</td>
<td valign="top">

Required

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-01-08

</td>
<td valign="top">

2024-01-08

</td>
</tr>
</table>

