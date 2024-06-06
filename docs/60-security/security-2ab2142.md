<!-- loio2ab214247ec942a7a5be16ac88b4dbdb -->

# Security

This guide provides an overview of the security-relevant information that applies to the SAP Task Center service.



<a name="loio2ab214247ec942a7a5be16ac88b4dbdb__section_zjy_h1b_t1c"/>

## SAP Task Center - Security Requirements and Setup



### SAP Cloud Identity Services – Identity Authentication

SAP Task Center federates tasks from multiple task providers. Each task provider assigns these tasks to its local users for processing.

At the same time, SAP Task Center is exposed on SAP BTP and business users authenticate on SAP BTP to access SAP Task Center. All task provider users must be created in the SAP Cloud Identity Services identity provider and must also be available on SAP BTP, which makes a common user base a must. For this purpose, SAP Task Center uses SAP Cloud Identity Services – Identity Authentication as a central identity provider across the whole landscape.

Each task provider that integrates with SAP Task Center must also be able to work with Identity Authentication. The SAP Cloud Identity Services - Identity Directory \(IdDS\) stores the SAP identities and the SAP Cloud Identity Services - Identity Authentication allow a secure authentication or a federation with 3rd party identity providers.

To be able to integrate with SAP Task Center, all task providers and the SAP Task Center must be configured to work with the same Identity Authentication tenant.



### Global User ID

In addition to a common identity and access management system with the task provider, SAP Task Center needs a deterministic and stable way to connect users and tasks.

For example, tasks must be connected to the same globally unique user identifier in SAP BTP and across all the provider systems.

Such an identifier is defined by Identity Authentication as the Global User ID.

The Global User ID is also a hard prerequisite for a SAP Task Center integration, as it allows a congruent and a performant integration across so many diverse applications and environments. Each one of the SAP Task Center task providers, whether SAP, or non-SAP applications, must be able to work with Identity Authentication and be able to map internal task-provider user identities to their respective Global User IDs. For more information on Global User ID, see [Global User ID in Integration Scenarios](https://help.sap.com/docs/cloud-identity/system-integration-guide/global-user-id-in-integration-scenarios).

SAP Task Center fetches tasks from multiple and various task providers and it relies on the Global User ID as a common user identifier, to be able to:

-   Identify which tasks should be shown to which users.

-   Enable action/response execution \(principal propagation\) and other operations, executed in the currently-signed-in user context.

-   Map Global User IDs to user details, such as display names, emails, etc. Those user details must also be populated or maintained in Identity Authentication.

-   Enable searching for and selecting a user in features such as task forwarding and creation of substitution rules.

-   Send notifications to users \(notifications are received by users signed into SAP BTP and again correlated via Global User ID\).

-   Enable other current and future functionalities.


![BTP services setup within a customer's subaccount for SAP Task Center. It includes user access, key components like SAP Build Work Zone, SAP Cloud Identity Services and other integrated services.](../10-what-is/images/SAP_Task_Center_Level_2_Diagram_07fe584.png)



### General Guidelines for the Integration with SAP Task Center

To integrate а task provider with SAP Task Center, the following general guidelines should be followed:

-   The users who would consume SAP Task Center must be available at both Identity Authentication and the task provider.

-   The user identities include the federation identifier - Global User ID, so that a user can be correlated across the different systems.

-   The user entries include essential user data, such as an e-mail address and display name.

-   Configure single sign-on between the 3rd party task provider and Identity Authentication to enable navigation between SAP Task Center and the task provider.

-   Tasks must be correlated with Global User ID when provided to SAP Task Center. For example, the list of recipient users of a task must contain Global User IDs.


For more information, see [System Integration Guide for SAP Cloud Identity Services](https://help.sap.com/docs/cloud-identity/system-integration-guide/system-integration-guide-for-sap-cloud-identity-services).

**Related Information**  


[Identity Provider and Identity Management](identity-provider-and-identity-management-69b3bae.md "For identity management and authentication, the SAP Task Center tenant relies on the Identity Authentication as the identity provider (IdP) that is configured in the customer subaccount that owns the respective subscriptions.")

[Authorization Configuration](authorization-configuration-75e4130.md "Assign roles to specific users using the SAP Task Center instance.")

[Assign Roles to Your Users](assign-roles-to-your-users-7e081d8.md "To assign roles to users, you need to add roles to one or more role collections and then assign these role collections to your users.")

[Data Protection and Privacy](data-protection-and-privacy-8bd310a.md "Governments place legal requirements on industry to protect data and privacy. We provide features and functions to help you meet these requirements.")

[Auditing and Logging Information](auditing-and-logging-information-09dcab2.md "Here you can find a list of the security events that are logged by the SAP Task Center service.")

[Credentials Rotation](credentials-rotation-8080abf.md "Change your credentials at regular intervals to ensure a higher level of security.")

[Security Guide for SAP Business Technology Platform \(SAP BTP\)](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e129aa20c78c4a9fb379b9803b02e5f6.html)

