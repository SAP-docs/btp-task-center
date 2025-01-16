<!-- loio092288d940e741738f3dd3d9a734ada7 -->

# Integration with SAP Cloud ALM

Use the integration of SAP Task Center with SAP Cloud ALM \(Application Lifecycle Management\) to monitor all inbound and outbound communication data events with the SAP Task Center REST API. This information pertains to events that a customer system administrator needs to know in order to troubleshoot critical issues, related to task management events.



<a name="loio092288d940e741738f3dd3d9a734ada7__section_w22_dyj_3bc"/>

## Prerequisites

To make the reporting of SAP Task Center events available in SAP Cloud ALM, make sure that:

-   You have completed the initial setup of SAP Task Center \(see [Initial Setup](../30-initial-setup/initial-setup-8347694.md)\).

-   You have set up and configured SAP Cloud ALM, as described in the *Getting started* section for [SAP Cloud ALM](https://support.sap.com/en/alm/sap-cloud-alm.html).

-   You have completed the mandatory setup for SAP Task Center, as described in [Setup for SAP Task Center](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/calm-setup-stc.html) and have activated the *Data Collection* for each monitoring application you plan to use with SAP Task Center as follows:

    -   For *Integration & Exception Monitoring*, activate the *Monitoring Data Collection* by following [Integration & Exception Monitoring - Setup & Configuration](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/int-mon-setup-support.html).
    -   For *Real User Monitoring*, activate the *Data Collection* by following [Real User Monitoring - Setup & Configuration](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/real-user-monitoring/run-details.html#section_194947898_co).




<a name="loio092288d940e741738f3dd3d9a734ada7__section_lbn_2yj_3bc"/>

## Using SAP Cloud ALM

Once you have completed the prerequisites, you can access the SAP Task Center monitoring content in your SAP Cloud ALM tenant.



### Integration & Exception Monitoring

In the *Integration & Exception Monitoring* application you can find all of the inbound and outbound messages with the SAP Task Center REST API. The monitoring represents a complex drill-down visualization of the respective business-technical information for a time period of up to 14 days in the past.

For more information on how to use the *Integration & Exception Monitoring* application, see [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring).



### Real User Monitoring

The *Real User Monitoring* application provides insights into application usage and performance by tracking user interactions and server requests. The monitoring provides you with detailed visualizations of the relevant server requests and all user interactions.

For more information on how to use *Real User Monitoring* application, see [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring).

**Related Information**  


[SAP Cloud ALM](https://help.sap.com/docs/cloud-alm)

