<!-- loio834769400794464489f390350a82bbd6 -->

# Initial Setup

To use the service, make sure you have performed the preliminary setup and meet the prerequisites. Then continue with the initial setup for SAP Task Center, following either the automatic setup \(using a booster\) or the manual setup.

> ### Tip:  
> ![](images/28x28_launch_png_2484bce.png) Check also the step-by-step mission for the initial setup [Establish a Central Inbox with SAP Task Center](https://discovery-center.cloud.sap/missiondetail/3774/3813/) on SAP Discovery Center.



<a name="loio834769400794464489f390350a82bbd6__section_rvy_tcp_pzb"/>

## Prerequisites

You can perform the initial setup for SAP Task Center following either the automatic setup \(using a booster\) or by manual setup. Before you start, make sure you meet all prerequisites.

![An interactive graphic of the four main prerequisites you need to
							complete before setting up the service.](images/Initial_Setup_727bcc8.png)



### Check Your Entitlements and Commercial Model

Make sure that you are entitled to create an instance of the SAP Task Center service and your global account uses the consumption-based commercial model.

For more information, see [What Is the Consumption-Based Commercial Model?](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/7047eb4a15a84ac7be3c8612179e6d1f.html).



### Prepare Your SAP Business Technology Platform \(SAP BTP\) Account

Prepare your SAP Business Technology Platform \(SAP BTP\) account by making sure that:

1.  You are a global account administrator.

    For more information, see [Getting a Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d61c2819034b48e68145c45c36acba6e.html#loiod61c2819034b48e68145c45c36acba6e).

2.  You have created a subaccount on Cloud Foundry in your global account.

    For more information, see [Relationship Between Global Accounts and Subaccounts](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loioeeda449cf252418a97e0f7c9abd30b9a) in [Account Model](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html).

3.  You have created a space within a subaccount in which Cloud Foundry is enabled.

    For more information, see [Getting Started in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/b328cc89ea14484d9655b8cfb8efb508.html).

4.  Within that space, your user is assigned to the *Space Developer* role for the subaccount. For more information, see [About Roles in the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/about-roles-in-cloud-foundry-environment). You need this role to perform the configuration steps.

    For more information, see [Add Space Members Using the Cockpit](https://help.sap.com/docs/btp/sap-business-technology-platform/add-space-members-using-cockpit).

5.  You have established trust with the User Account and Authentication \(UAA\) of your subaccount, using Identity Authentication.

    Identity Authentication is mandatory for working with SAP Task Center.

    For more information, see [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html) or [Manually Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/7c6aa87459764b179aeccadccd4f91f3.html).




### Integrate with SAP Cloud Identity Services

For the integration with SAP Cloud Identity Services, you must have followed the integration guide \(see [System Integration Guide for SAP Cloud Identity Services](https://help.sap.com/viewer/b95c3d5bab324a3a8409eee5267a5b75/Cloud/en-US)\) and have completed the integration scenario setup for the task providers, which you would like to configure.

For the integration with SAP Advanced Financial Closing, SAP Build Process Automation or SAP Build Work Zone, advanced edition as task provider, make sure you follow the [SAP BTP Integration Scenario](https://help.sap.com/docs/cloud-identity/system-integration-guide/sap-btp-integration-scenario?version=Cloud).

> ### Caution:  
> -   All task providers and the SAP Task Center UAA of your subaccount must be configured to work with the same Identity Authentication tenant.
> -   Make sure that the *Display Name*, *E-Mail* and *Global User ID* fields are maintained for every user in your Identity Authentication tenant. For more information, see [Global User ID in Integration Scenarios](https://help.sap.com/docs/SAP_CLOUD_IDENTITY/b95c3d5bab324a3a8409eee5267a5b75/a04611df60404a248a7a8089c85b9761.html) and [List and Edit User Details](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/045cb01bd2034b05a69e1a626e46570f.html).
> 
>     Note, that **None** should not be defined as *Display Name* in Identity Authentication, as it is reserved for technical usage.



### Verify Your Central Point of Entry for Accessing Applications

You have a subscription to at least one of the following services in the same subaccount as your SAP Task Center subscription:

-   SAP Build Work Zone, standard edition, formerly known as SAP Launchpad service

    The SAP Build Work Zone, standard edition is also available in free tier. For more information, see [Initial Setup](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/initial-setup) and [Using an Account with a Free Service Plan](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/1868e0dd101a4aa78b75e49ab46c992a.html).

-   [SAP Build Work Zone, advanced edition](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/onboarding-to-sap-build-work-zone-advanced-edition)

-   SAP Start \(For more information, see [Restrictions](https://help.sap.com/docs/start/sap-start/restrictions?q=To).\)

-   [SAP SuccessFactors Work Zone](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/onboarding-to-sap-successfactors-work-zone) \(for existing subscriptions only\)

-   [SAP Cloud Portal service](https://help.sap.com/docs/cloud-portal-service/sap-cloud-portal-service-on-cloud-foundry/what-is-cloud-portal-service)


> ### Note:  
> Please make sure that you check also the existing conventions and restrictions in the official documentation of your central point of entry for accessing applications.



<a name="loio834769400794464489f390350a82bbd6__section_ssw_jb2_2vb"/>

## Procedure

To use the SAP Task Center service, you must complete the initial setup either by using the booster \(recommended\) or by following the manual steps.

-   \(Recommended\) Set up the SAP Task Center service using the booster. See [Automatic Setup](automatic-setup-3a49967.md).

-   Set up the SAP Task Center service manually. See [Manual Setup](manual-setup-0f00d3d.md).


