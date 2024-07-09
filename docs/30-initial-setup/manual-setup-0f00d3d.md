<!-- loio0f00d3d3e2ab460c856d409c469fb4f1 -->

# Manual Setup

Get started with the SAP Task Center service using the standard procedures for SAP BTP, Cloud Foundry environment.



<a name="loio0f00d3d3e2ab460c856d409c469fb4f1__prereq_j2b_42y_j4b"/>

## Prerequisites

Before you continue with the manual setup, make sure you meet the following prerequisites:

-   You have completed all prerequisites listed in [Initial Setup](initial-setup-8347694.md).

-   Your subaccount is entitled to use SAP Task Center with a *standard* plan.

    For more information, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html).




## Procedure

1.  Navigate to the space in the SAP BTP cockpit that you created as part of the prerequisites.

2.  Create a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

3.  \(Optional\) Create a service key for the service instance.

    For more information, see [Creating Service Keys in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6fcac08409db4b0f9ad55a6acd4d31c5.html) in the SAP Business Technology Platform \(SAP BTP\) documentation.

4.  Set up the service destinations and connect the SAP Task Center service to the SAP task provider solutions via destination configurations.

    For more information, see [Destinations](../40-administration/destinations-3470733.md).

5.  Configure the consumer content of your central point of entry for accessing apps for the SAP Task Center Web app.

    For more information, see [Create a Task Center Tile](create-a-task-center-tile-70e7f6e.md).


**Related Information**  


[Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md "Create a service instance for the SAP Task Center service either in the cockpit or by using the command-line interface.")

[Create a Task Center Tile](create-a-task-center-tile-70e7f6e.md "Create a Task Center tile by following the links.")

[Create a Task Center Administration Tile](create-a-task-center-administration-tile-8053d72.md "Create a Task Center Administration tile by folloing the links below.")

