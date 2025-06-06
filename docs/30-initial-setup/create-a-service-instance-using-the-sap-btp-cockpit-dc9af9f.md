<!-- loiodc9af9fd363b4e989af6ff2f19548d32 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Service Instance Using the SAP BTP Cockpit

You can create an instance of the SAP Task Center service using the SAP BTP cockpit.



<a name="loiodc9af9fd363b4e989af6ff2f19548d32__context_msg_lfw_c3b"/>

## Context

In SAP BTP, Cloud Foundry environment, you enable services by creating a service instance using either the SAP BTP cockpit or the Cloud Foundry command-line interface \(CLI\), and binding that instance to your application. A service instance is a single instantiation of a service running on SAP Business Technology Platform \(SAP BTP\). For more information, see [About Services](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d1d0fc8e78474494a59caad02259ec7e.html).

The service instance of SAP Task Center scales dynamically according to usage; creating additional service instances has no impact on the available resources. All service instances within the same organization share the same data.

> ### Caution:  
> As soon as you delete the last service instance of the SAP Task Center across all the spaces in your organization, all your data within SAP Task Center is erased irrevocably.



<a name="loiodc9af9fd363b4e989af6ff2f19548d32__steps_a15_r2w_c3b"/>

## Procedure

1.  Navigate to your space in the SAP BTP cockpit.

2.  In the navigation area under *Services*, choose *Service Marketplace*.

3.  Choose the *SAP Task Center* tile.

4.  Choose *Create*.

5.  In the wizard, make sure that the service is set to *SAP Task Center*, choose a service plan \(*all-tasks* service plan is recommended\), then enter a name for the instance, and choose *Next*.

6.  Check the overview, and then choose *Create*.

    The new instance appears on the *Instances* page after a short while.

7.  \(Optional\) Create a service key for the service instance.

    You need a service key if you want to call the service API standalone without a UI, for example, from Postman.

    1.  On the *Instances* page, select the service instance and at the end of the row open the *Actions* menu \(<span class="SAP-icons-V5"></span>\).

    2.  Choose *Create Service Key*.

        You can create a service key with or without a certificate. The certificate is required when setting up an mTLS communication.

        -   Create a service key \(without certificate\).

            In the *New Service Key* wizard, choose a name for your service key, and choose *Create*.

        -   Create a service key with certificate.

            To create a service key with certificate for mTLS communication, proceed as follows:

            1.  In the *New Service Key* wizard, choose a name for your service key and specify the following parameters in JSON format:

                > ### Sample Code:  
                > ```
                > {
                >     "xsuaa": {
                >         "credential-type": "x509",
                >         "x509": {
                >             "key-length": 2048,
                >             "validity": 1,
                >             "validity-type": "YEARS"
                >         }
                >     }
                > }
                > ```

                Keep in mind that the maximum validity of this certificate is one year \(defined in years, months, days, and so on\).

            2.  Choose *Create*.


        > ### Note:  
        > If your SAP Task Center service instance was created before May 2022, you might have to update your service instance before creating a service key with certificate for mTLS communication. Follow the steps in [Updating Service Instances](https://help.sap.com/docs/service-manager/sap-service-manager/updating-service-instances) and add the following instance parameters:
        > 
        > > ### Sample Code:  
        > > ```
        > > {
        > >     "authorities": [],
        > >     "defaultCollectionQueryFilter": "own",
        > >     "xs-security": {
        > >         "oauth2-configuration": {
        > >             "credential-types": [
        > >                 "binding-secret",
        > >                 "instance-secret",
        > >                 "x509"
        > >             ]
        > >         }
        > >     }
        > > }
        > > ```


    For more information, see [Create Service Keys Using the Cockpit](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6fcac08409db4b0f9ad55a6acd4d31c5.html) in the SAP Business Technology Platform \(SAP BTP\) documentation.


