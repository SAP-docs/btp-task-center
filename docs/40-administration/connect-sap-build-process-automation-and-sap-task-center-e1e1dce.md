<!-- loioe1e1dce7e52249f78370e5b05d3bce88 -->

# Connect SAP Build Process Automation and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from SAP Build Process Automation on SAP BTP, Cloud Foundry environment.



<a name="loioe1e1dce7e52249f78370e5b05d3bce88__section_v3f_3gw_wtb"/>

## Prerequisites

-   You must have performed the steps in [Configure the SAP Build Process Automation Subaccount for SAP Task Center](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/4f04949597e84e18ae429d0bc280f4a2.html). From the service key of the SAP Build Process Automation instance in the Cloud Foundry environment you need the values of the following parameters for the setup of the destinations:

    -   `endpoints > api`
    -   `uaa > clientid`
    -   `uaa > clientsecret`
    -   `uaa > url`

    For more information, see [Determine Service Configuration Parameters](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/abd070bd5d5f4835b3d5b12d868531b6.html).

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).




<a name="loioe1e1dce7e52249f78370e5b05d3bce88__section_odq_2fh_55b"/>

## Procedure

In SAP Task Center you can receive tasks from an SAP Build Process Automation instance in the same \(local\) subaccount as the SAP Task Center instance, or from an instance in a different \(remote\) subaccount. Choose one of the options below, depending on your setup:

-   Create a destination for SAP Build Process Automation for a local subaccount. For more information, see [Work with SAP Build Process Automation Tasks from a Local Subaccount](work-with-sap-build-process-automation-tasks-from-a-local-subaccount-f9c57ee.md).

-   Create a destination for SAP Build Process Automation for a remote subaccount. For more information, see [Work with SAP Build Process Automation Tasks from a Remote Subaccount](work-with-sap-build-process-automation-tasks-from-a-remote-subaccount-1d3e69d.md).


