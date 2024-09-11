<!-- loio2873c51eb5a74e64a859f4be66ea7fa4 -->

# Connect SAP Advanced Financial Closing and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from SAP Advanced Financial Closing on SAP BTP, Cloud Foundry environment.



<a name="loio2873c51eb5a74e64a859f4be66ea7fa4__section_v3f_3gw_wtb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](../30-initial-setup/initial-setup-8347694.md). Make sure you have followed the [SAP BTP Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-btp-integration-scenario).

-   You must have performed the required setup described in [SAP Task Center Integration for SAP Advanced Financial Closing](https://help.sap.com/docs/advanced-financial-closing/administration/sap-task-center-integration-for-sap-advanced-financial-closing).

    From the service key of the SAP Advanced Financial Closing instance in the Cloud Foundry environment you need the values of the following parameters for the setup of the destinations:

    -   `endpoints > task-center`
    -   `uaa > clientid`
    -   `uaa > clientsecret`
    -   `uaa > url`




<a name="loio2873c51eb5a74e64a859f4be66ea7fa4__section_odq_2fh_55b"/>

## Procedure

In SAP Task Center you can receive tasks from an SAP Advanced Financial Closing instance in the same subaccount as the SAP Task Center instance, or from an instance in a different subaccount. Choose one of the options below, depending on your setup:

-   Create a destination for SAP Advanced Financial Closing, where SAP Advanced Financial Closing and SAP Task Center are in the same subaccount. For more information, see [Work with SAP Advanced Financial Closing Tasks from the Same Subaccount](work-with-sap-advanced-financial-closing-tasks-from-the-same-subaccount-e28e2af.md).

-   Create a destination for SAP Advanced Financial Closing, where SAP Advanced Financial Closing and SAP Task Center are in different subaccounts. For more information, see [Work with SAP Advanced Financial Closing Tasks from a Different Subaccount](work-with-sap-advanced-financial-closing-tasks-from-a-different-subaccount-09cee80.md).


