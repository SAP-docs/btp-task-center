<!-- loio2873c51eb5a74e64a859f4be66ea7fa4 -->

# Connect SAP Advanced Financial Closing and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from SAP Advanced Financial Closing on SAP BTP, Cloud Foundry environment.



<a name="loio2873c51eb5a74e64a859f4be66ea7fa4__section_v3f_3gw_wtb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP BTP Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-btp-integration-scenario).

-   You must have performed the required setup descirbed in [SAP Task Center Integration for SAP Advanced Financial Closing](https://help.sap.com/docs/advanced-financial-closing/administration/sap-task-center-integration-for-sap-advanced-financial-closing).

    From the service key of the SAP Advanced Financial Closing instance in the Cloud Foundry environment you need the values of the following parameters for the setup of the destinations:

    -   `endpoints > task-center`
    -   `uaa > clientid`
    -   `uaa > clientsecret`
    -   `uaa > url`




<a name="loio2873c51eb5a74e64a859f4be66ea7fa4__section_odq_2fh_55b"/>

## Procedure

In SAP Task Center you can receive tasks from an SAP Advanced Financial Closing instance in the same \(local\) subaccount as the SAP Task Center instance, or from an instance in a different \(remote\) subaccount. Choose one of the options below, depending on your setup:

-   Create a destination for SAP Advanced Financial Closing for a local subaccount. For more information, see [Work with SAP Advanced Financial Closing Tasks from a Local Subaccount](work-with-sap-advanced-financial-closing-tasks-from-a-local-subaccount-e28e2af.md).

-   Create a destination for SAP Advanced Financial Closing for a remote subaccount. For more information, see [Work with SAP Advanced Financial Closing Tasks from a Remote Subaccount](work-with-sap-advanced-financial-closing-tasks-from-a-remote-subaccount-09cee80.md).


