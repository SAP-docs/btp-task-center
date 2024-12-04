<!-- loioe1e1dce7e52249f78370e5b05d3bce88 -->

# Connect SAP Build Process Automation and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from SAP Build Process Automation on SAP BTP, Cloud Foundry environment.



<a name="loioe1e1dce7e52249f78370e5b05d3bce88__section_v3f_3gw_wtb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP BTP Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-btp-integration-scenario).

-   You must have performed the steps in [Configure the SAP Build Process Automation Subaccount for SAP Task Center](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/4f04949597e84e18ae429d0bc280f4a2.html).

    From the service key of the SAP Build Process Automation instance in the Cloud Foundry environment you need the values of the following parameters for the setup of the destinations:

    -   `endpoints > api`
    -   `uaa > clientid`
    -   `uaa > clientsecret`

    For more information, see [Determine Service Configuration Parametersuaa \> url](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/abd070bd5d5f4835b3d5b12d868531b6.html).




<a name="loioe1e1dce7e52249f78370e5b05d3bce88__section_odq_2fh_55b"/>

## Procedure

In SAP Task Center you can receive tasks from an SAP Build Process Automation instance in the same subaccount as the SAP Task Center instance, or from an instance in a different subaccount. Choose one of the options below, depending on your setup:

-   Create a destination for SAP Build Process Automation, where SAP Build Process Automation and SAP Task Center are in the same subaccount. For more information, see [Work with SAP Build Process Automation Tasks from the Same Subaccount](work-with-sap-build-process-automation-tasks-from-the-same-subaccount-f9c57ee.md).

-   Create a destination for SAP Build Process Automation, where SAP Build Process Automation and SAP Task Center are in different subaccounts. For more information, see [Work with SAP Build Process Automation Tasks from a Different Subaccount](work-with-sap-build-process-automation-tasks-from-a-different-subaccount-1d3e69d.md).

-   \(Optional\) Create a destination for the *Intelligent Recommendations* feature. For more information, see [Configure the Intelligent Recommendations Destination](configure-the-intelligent-recommendations-destination-7c8900a.md).


