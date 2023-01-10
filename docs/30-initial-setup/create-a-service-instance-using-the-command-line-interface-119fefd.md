<!-- loio119fefdbbe354757b390ee6bdb35953c -->

# Create a Service Instance Using the Command-Line Interface

You can create the instance of SAP Task Center service using the command-line interface.



<a name="loio119fefdbbe354757b390ee6bdb35953c__prereq_mts_jwl_qbb"/>

## Prerequisites

-   Install the Cloud Foundry command-line interface \(cf CLI\).

    For more information, see [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4ef907afb1254e8286882a2bdef0edf4.html) and [Log On to the Cloud Foundry Environment Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7a37d66c2e7d401db4980db0cd74aa6b.html).

-   Log on to your organization and space using the Cloud Foundry command-line interface.

    For more information, see [Creating Spaces Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/a2e5e29eca0b40da8d3a25e806329377.html).




<a name="loio119fefdbbe354757b390ee6bdb35953c__context_xn1_w3w_c3b"/>

## Context

In the Cloud Foundry environment, you enable services by creating a service instance using either the SAP BTP cockpit or the Cloud Foundry cf CLI, and binding that instance to your application. A service instance is a single instantiation of a service running on SAP Business Technology Platform \(SAP BTP\). For more information, see [About Services](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d1d0fc8e78474494a59caad02259ec7e.html).

The service instance of the SAP Task Center scales dynamically according to usage; creating additional service instances has no impact on the available resources. All service instances within the same organization share the same data.

> ### Caution:  
> As soon as you delete the last remaining service instance of the SAP Task Center across all the spaces in your organization, all your data within the SAP Task Center is erased irrevocably.



<a name="loio119fefdbbe354757b390ee6bdb35953c__steps_rmx_j3w_c3b"/>

## Procedure

1.  Check that SAP Task Center is available in the marketplace:

    ```
    cf marketplace
    ```

    You can see a service named SAP Task Center with a plan named *standard*.

2.  Create a service instance of the SAP Task Center:

    ```
    cf create-service one-inbox-service standard <inbox_instance>
    ```

    Specify the following parameters:

    -   `SERVICE`: The name of the service that you want to create an instance of. In the example above: `inbox`.

    -   `PLAN`: The name of the service plan that you want to use. In the example above: `standard`.

    -   `SERVICE_INSTANCE`: The new name for your service instance. Use only alphanumeric characters, hyphens, and underscores. In the example above: `inbox_instance`.



