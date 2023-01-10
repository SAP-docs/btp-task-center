<!-- loioeae23f3a679d481295ff05bdb322f859 -->

# Connect SAP SuccessFactors and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with task from SAP SuccessFactors on SAP BTP, Cloud Foundry environment.



<a name="loioeae23f3a679d481295ff05bdb322f859__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have executed the steps in [Enabling To-Do Task Integration Between SAP SuccessFactors and SAP Task Center](https://help.sap.com/viewer/568480cc877d4337992a2cd9792fbfed/latest/en-US/c15f23f6f4e24ddea84d5be8e6b935ae.html).

-   You have completed all prerequisites listed in [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).


> ### Note:  
> Do not configure more than one primary destination to the same SAP SuccessFactors system for each SAP Task Center. This will result in having duplicate tasks for end users.



## Procedure

1.  In the SAP BTP cockpit, export your trust certificate:

    1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select *Connectivity* \> *Destinations* from the navigation area on the left.

    2.  Choose *Download Trust*.
    3.  Save the trust certificate file locally.

    > ### Caution:  
    > Make sure to renew you trust certificate before it expires. For the time while you are renewing the trust certificate and updating it on the task provider systems you may not be able to work on tasks, nor receive task updates.
    > 
    > For more information, see [Renew Destination Trust Certificates](../60-security/credentials-rotation-8080abf.md#loio8080abf7d2cf4918802aa86e955ffc8b__section_RenewTrust).

2.  Create a primary destination with the technical user, as described in [Creating the Primary Destination with the Technical User](creating-the-primary-destination-with-the-technical-user-dc5407b.md).

3.  Create a secondary destination for the principal propagation, as described in [Creating a Secondary Destination for the Principal Propagation](creating-a-secondary-destination-for-the-principal-propagation-bf657f8.md).


