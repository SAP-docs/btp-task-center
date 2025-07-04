<!-- loioc45c4c34eb794df885ffccb94226e0a5 -->

# Access the SAP Task Center API Using Identity Authentication

Access the SAP Task Center API by utilizing direct authentication via SAP Cloud Identity Services - Identity Authentication.



<a name="loioc45c4c34eb794df885ffccb94226e0a5__section_vbd_hsk_w2c"/>

## Prerequisites

-   You have completed the [Initial Setup](../30-initial-setup/initial-setup-8347694.md) and as a result you have created a service instance of the SAP Task Center, created either by the booster deployment or manually.
-   You have assigned the necessary role collections of the SAP Task Center API to the user on whose behalf the call to the SAP Task Center API is performed. If you have completed the [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md), your user already has the necessary permissions.

    For more information about role collections, see [Assign Roles to Your Users](../60-security/assign-roles-to-your-users-7e081d8.md).

    For more information about the SAP Task Center roles, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loioc45c4c34eb794df885ffccb94226e0a5__section_f3f_t2l_w2c"/>

## Context

By completing this procedure, you allow a consumer application to consume the API of SAP Task Center.



<a name="loioc45c4c34eb794df885ffccb94226e0a5__section_vpq_hsk_w2c"/>

## Procedure

1.  Make sure that you have a subscription to the SAP Task Center service. This subscription might have been automatically created if you have used the booster \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\). In this case you'll be able to see the subscription to the SAP Task Center service in *Services* \> *Instances and Subscriptions* \> *Subscriptions*.

    In case that a subscription to the SAP Task Center service is not available, create one by following the steps:

    1.  In the navigation area of your subaccount, choose *Services* \> *Service Marketplace*.
    2.  Choose the SAP Task Center tile and choose *Create*.
    3.  In the wizard, make sure that the service is set to SAP Task Center. Then, select one of the plans of type *Subscription* and choose *Create*.

2.  Define a dependency to the SAP Task Center API as provider application as described in [Configure Integration Between Applications](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/communicate-between-applications).
3.  Consume the SAP Task Center API using the defined dependency. For more information, see [Consume an API from a Provider Application](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/consume-api-from-another-application).

