<!-- loio8080abf7d2cf4918802aa86e955ffc8b -->

# Credentials Rotation

Change your credentials at regular intervals to ensure a higher level of security.



<a name="loio8080abf7d2cf4918802aa86e955ffc8b__section_ClientCredentials"/>

## Rotate Client Credentials

To get a new `clientsecret`, create a new service key for a service instance and exchange it in the task provider setup.

By creating a new service key, only the `clientsecret` changes and the other parameters remain the same.



### Rotate Credentials for SAP Fieldglass

1.  Create a new service key for the existing service instance, which you created in step *Create a new service instance to enable task updates to be pushed from SAP Fieldglass* in [Connect SAP Fieldglass and SAP Task Center](../40-administration/connect-sap-fieldglass-and-sap-task-center-9367f0d.md).

2.  Copy the new `clientsecret` and update it in the *Setup* dialog box in your SAP Fieldglass system. For more information, see [Manage SAP Task Center to Enable Push of Task Updates](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/028e198df0284ff09662aa279a25b00f.html).



### Rotate Credentials for SAP S/4HANA Cloud

1.  Create a new service key for the existing service instance, which you created in step *Create a dedicated service instance for SAP Task Center in the Cloud Foundry subaccount, where your initial SAP Task Center instance was created* in [Connect SAP S/4HANA Cloud and SAP Task Center](../40-administration/connect-sap-s-4hana-cloud-and-sap-task-center-0aff1b4.md).

2.  Copy the new `clientsecret` and update it in the *Edit Outbound User* dialog box in your SAP S/4HANA Cloud system. For more information, see *Users for Outbound Communication* in [Create a Communication Arrangement](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/913ff1a47a6447e3b7bee17fa6f275ff.html?version=latest).



### Rotate Credentials for SAP SuccessFactors

1.  Create a new service key for the existing service instance, which you created in step *Create a new service instance to enable task updates to be pushed from SAP SuccessFactors* in [Creating the Primary Destination with the Technical User](../40-administration/creating-the-primary-destination-with-the-technical-user-dc5407b.md).

2.  Copy the new `clientsecret` and update it on the *Integration Service Registration Center* page in your SAP SuccessFactors system. For more information, see [Enabling Push of Task Updates to SAP Task Center](https://help.sap.com/viewer/568480cc877d4337992a2cd9792fbfed/latest/en-US/f65742cc51034ae595c3e0c688418944.html).

Once you confirm that the setup with the updated `clientsecret` is working properly, you can delete the old service key.



<a name="loio8080abf7d2cf4918802aa86e955ffc8b__section_RenewTrust"/>

## Renew Destination Trust Certificates

Renew your certificates at regular intervals to ensure secure communication between SAP Task Center and the task provider systems.

Follow the steps in [Rotate Certificates](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/82dbecae3454493782d16a79e30f1a6d.html?version=Cloud#rotate-certificates) and make sure to update the new certificate in the respective task provider system:

-   For SAP Ariba, see more about the how to request IDP registration on the SAP Ariba OAuth in [Connect SAP Ariba and SAP Task Center](../40-administration/connect-sap-ariba-and-sap-task-center-d26b525.md).
-   For SAP Fieldglass, see [Establishing Trust with Destination Service](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/3fabeb5092a44edd8fc3dd4b4cbc6b9e.html).
-   For SAP S/4HANA Cloud, see [Create a Communication System](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/be1e3da9ea1446a0ac9bbcbe36fb08a2.html).
-   For SAP SuccessFactors, see [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/568480cc877d4337992a2cd9792fbfed/latest/en-US/6b3c741483de47b290d075d798163bc1.html).

> ### Tip:  
> It is highly recommended to renew the certificate during maintenance windows or out of business hours.
> 
> We recommend you to renew the destination trust certificates by following the steps in [Rotate Certificates](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/82dbecae3454493782d16a79e30f1a6d.html?version=Cloud#rotate-certificates). This way you should not experience any downtime for your system.
> 
> If you prefer following [Renew a Certificate](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/82dbecae3454493782d16a79e30f1a6d.html#loio82dbecae3454493782d16a79e30f1a6d__renew_cert), for the time while you are renewing the trust certificate and updating it on the task provider systems, you may not be able to work on tasks, nor receive task updates.

