<!-- loiof354ef9cab4641219fd849102d1b5b0c -->

# Connect SAP Concur and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from SAP Concur Expense or SAP Concur Request on SAP BTP, Cloud Foundry environment.



<a name="loiof354ef9cab4641219fd849102d1b5b0c__section_v3f_3gw_wtb"/>

## Prerequisites

> ### Tip:  
> ![](../30-initial-setup/images/28x28_launch_png_2484bce.png) See also the step-by-step mission for the setup of connection to SAP Concur at [Integrate Your SAP Concur Tasks Into SAP Task Center](https://discovery-center.cloud.sap/missiondetail/3883/3962/).

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP Concur Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-concur-integration-scenario).

-   You have an existing SAP Concur entity, and have generated the `Company Request Token` and `Company UUID`. For more information, see [SAP Concur Company Request Token](https://help.sap.com/docs/SAP_CONCUR/384ace1050b34555a6fed7ad1e49e2eb/1b9049306caf101495ce810462271ffb.html).

    If you need any additional information, contact your SAP Concur implementation consultant.

-   You have enabled the workflows for Concur Expense, Concur Request, or both, for SAP Task Center. For more information, see [SAP Task Center Integration with Concur Solutions](https://help.sap.com/docs/SAP_CONCUR/384ace1050b34555a6fed7ad1e49e2eb/1b9360de6caf1014a1c2f9558d278c18.html).

-   You have opened a ticket to verify your Data Privacy Agreement version.

    To verify if you have the latest Data Privacy Agreement version, please open a ticket through the [SAP Support Portal](https://support.sap.com/), using the **BNS-CON-TSK** component. Use "SAP Concur DPA Version Verification" as subject of the ticket and ask the SAP colleagues to verify your Data Privacy Agreement version. If you don’t have the latest version, you will be prompted to sign a new Data Privacy Agreement and send it back via the ticket.


> ### Note:  
> Do not configure more than one destination to the same SAP Concur entity or product combination for one SAP Task Center. This will result in having duplicate tasks for end users.



<a name="loiof354ef9cab4641219fd849102d1b5b0c__section_odq_2fh_55b"/>

## Procedure

The SAP Concur entity may have Concur Expense, Concur Request, or both products. You have to create separate destinations for each product \(Concur Expense and Concur Request\). The *URL* specifies whether the destination is for Concur Expense or Concur Request. Each destination should have a unique combination of the fields *URL* and *Client Key*.

-   Create a destination for SAP Concur Expense, see [Connect SAP Concur Expense and SAP Task Center](connect-sap-concur-expense-and-sap-task-center-a087adb.md).

-   Create a destination for SAP Concur Request, see [Connect SAP Concur Request and SAP Task Center](connect-sap-concur-request-and-sap-task-center-65bd21c.md).


