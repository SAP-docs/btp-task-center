<!-- loioc6362b6a82904ac7836c3e2f3dc871cd -->

# Connect a Third-Party Task Provider and SAP Task Center

Find information about the destination configuration that needs to be done for SAP Task Center in order to work with tasks from a third-party task provider.



<a name="loioc6362b6a82904ac7836c3e2f3dc871cd__prereq_zzy_spz_pjb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center \(see [Initial Setup](../30-initial-setup/initial-setup-8347694.md)\) and have followed the [Third-Party Scenarios](https://help.sap.com/docs/cloud-identity/system-integration-guide/third-party-integration) documentation for the integration with SAP Cloud Identity Services.

-   You have a third-party task provider tenant with an existing SPI implementation, according to the description in SAP Note [3462266](https://me.sap.com/notes/3462266).

    You need the values of the following properties:

    -   URL

    -   Authentication and the respective credentials and additional properties, depending on your authentication method.


    These properties should be available in the third-party task provider documentation.

    > ### Note:  
    > Please note that connecting an on-premise third-party task provider is currently not supported.




## Procedure

1.  Create a primary destination with the technical user, as described in [Primary Destination with the Technical User \(Third-Party Task Provider\)](primary-destination-with-the-technical-user-third-party-task-provider-b55629f.md).

2.  Create a secondary destination for the principal propagation, as described in [Secondary Destination for the Principal Propagation \(Third-Party Task Provider\)](secondary-destination-for-the-principal-propagation-third-party-task-provider-1a6be2c.md).


