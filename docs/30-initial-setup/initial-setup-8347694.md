<!-- loio834769400794464489f390350a82bbd6 -->

# Initial Setup

Make sure you meet the prerequisites before you perform the initial setup for SAP Task Center, following either the automatic setup \(using a booster\) or the manual setup.



<a name="loio834769400794464489f390350a82bbd6__section_z3b_p3y_x5b"/>

## Prerequisites

Before you can use the service, meet the following prerequisites and perform the initial setup.

-   You are entitled to create an instance of the SAP Task Center service and your global account uses the consumption-based commercial model.

    For more information, see [What Is the Consumption-Based Commercial Model?](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/7047eb4a15a84ac7be3c8612179e6d1f.html).

-   Prepare your SAP Business Technology Platform \(SAP BTP\) account by making sure that:

    1.  You are a global account administrator.

        For more information, see [Getting a Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d61c2819034b48e68145c45c36acba6e.html#loiod61c2819034b48e68145c45c36acba6e).

    2.  You have created a subaccount on Cloud Foundry in your global account.

        For more information, see [Relationship Between Global Accounts and Subaccounts](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loioeeda449cf252418a97e0f7c9abd30b9a) in [Account Model](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html).

    3.  You have created a space within a subaccount in which Cloud Foundry is enabled.

        For more information, see [Getting Started in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/b328cc89ea14484d9655b8cfb8efb508.html).

    4.  Within that space, your user is assigned to the *Space Developer* role for the subaccount. You need this role to execute the configuration steps.

        For more information, see [User and Member Management](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/cc1c676b43904066abb2a4838cbd0c37.html).

    5.  Establish trust with the User Account and Authentication \(UAA\) of your subaccount, using Identity Authentication.

        Identity Authentication is mandatory for working with SAP Task Center.

        For more information, see [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html) or [Manually Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/7c6aa87459764b179aeccadccd4f91f3.html).


-   Integration with SAP Cloud Identity Service

    You have followed the integration guide for SAP Cloud Identity Services and have completed the integration scenario setup for the task providers, which you would like to configure.

    For more information, see [System Integration Guide for SAP Cloud Identity Services](https://help.sap.com/viewer/b95c3d5bab324a3a8409eee5267a5b75/Cloud/en-US).

    > ### Caution:  
    > -   All task providers and the SAP Task Center UAA of your subaccount must be configured to work with the same Identity Authentication tenant.
    > -   Make sure that the *Display Name*, *E-Mail* and *Global User ID* fields are maintained for every user in your Identity Authentication tenant. For more information, see [List and Edit User Details](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/045cb01bd2034b05a69e1a626e46570f.html) and [Global User ID in Integration Scenarios](https://help.sap.com/docs/SAP_CLOUD_IDENTITY/b95c3d5bab324a3a8409eee5267a5b75/a04611df60404a248a7a8089c85b9761.html).

-   You have purchased at least one of the following central points of entry for accessing apps and it is available in your global account.

    -   SAP Build Work Zone, standard edition, formerly known as SAP Launchpad service

        The SAP Build Work Zone, standard edition is also available in free tier. For. more information, see [Initial Setup](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/fd79b232967545569d1ae4d8f691016b.html) and [Using an Account with a Free Service Plan](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/1868e0dd101a4aa78b75e49ab46c992a.html).

    -   SAP Build Work Zone, advanced edition

    -   SAP SuccessFactors Work Zone

    -   SAP Cloud Portal service


    > ### Note:  
    > Having subscriptions on both SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone on the same subaccount isn't supported. If you are already using SAP SuccessFactors Work Zone in your subaccount, you will need to either choose a different subaccount or unsubscribe before you on board to SAP Build Work Zone, advanced edition. For more information, see [SAP Build Work Zone, Advanced Edition Administrator Guide](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/9e78b62e8d2a4e1b928d85d22fe957a7.html#create-a-subaccount).




<a name="loio834769400794464489f390350a82bbd6__section_ssw_jb2_2vb"/>

## Procedure

To use the SAP Task Center service, you must complete the initial setup either by using the booster \(recommended\) or by following the manual steps.

-   \(Recommended\) Set up the SAP Task Center service using the booster. See [Automatic Setup](automatic-setup-3a49967.md).

-   Set up the SAP Task Center service manually. See [Manual Setup](manual-setup-0f00d3d.md).


