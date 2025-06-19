<!-- loio4a61a2586a8c46b893b621f22a50df8f -->

# Connect SAP Field Service Management and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP Field Service Management on SAP BTP, Cloud Foundry environment.



<a name="loio4a61a2586a8c46b893b621f22a50df8f__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html). Make sure you have followed the [SAP Field Service Management Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-field-service-management-integration-scenario).

-   You have performed the steps in [SAP Task Center Integration](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_integration/task-center-integration.html). You need the values of the following parameters for the setup of the destinations:

    -   *FSM cluster url*

        It should follow the pattern: `https://{cluster}.fsm.cloud.sap/cloud-approval-service/api`. For more information, see [Initial System Access](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_getting_started/initial-system-access.html).

    -   *FSM account id*

        For more information on your account ID, see [Account](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_admin/account.html).

    -   *FSM company ID*

        For more information on your company ID, see [Companies](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_admin/companies.html).

    -   *Client ID* and *Client Secret*

        For more information, see [Generating Client ID and Secret](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_admin/generating-client-id.html).

    -   *SAML metadata*

        For more information, see [SAML configuration for Field Service Management](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_federated_authentication/configure-cloud-account-in-admin.html).


-   You have downloaded your trust certificate from your Cloud Foundry subaccount, where your SAP Task Center instance was created, and have uploaded the certificate to FSM Admin portal as described in [Establish Trust with SAP Destination Service](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_integration/task-center-establish-trust-with-destination-service.html).

    > ### Caution:  
    > Make sure to renew you trust certificate before it expires. For the time while you are renewing the trust certificate and updating it on the task provider systems you may not be able to work on tasks, nor receive task updates. For more information, see [Renew Destination Trust Certificates](../60-security/credentials-rotation-8080abf.md#loio8080abf7d2cf4918802aa86e955ffc8b__section_RenewTrust).




## Procedure

1.  Create a primary destination with the technical user, as described in [Primary Destination with the Technical User \(SAP Field Service Management\)](primary-destination-with-the-technical-user-sap-field-service-management-5495960.md).

    > ### Note:  
    > Do not configure more than one primary destination to the same SAP Field Service Management system for each SAP Task Center. This will result in having duplicate tasks for end users.

2.  Create a secondary destination for the principal propagation, as described in [Secondary Destination for the Principal Propagation \(SAP Field Service Management\)](secondary-destination-for-the-principal-propagation-sap-field-service-management-2fef2f5.md).


