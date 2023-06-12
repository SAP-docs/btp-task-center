<!-- loiof0f13bf49e3f45488bcf24218a2771e4 -->

# Conventions and Technical Restrictions

These conventions and restrictions apply to the SAP Task Center.

Considering this information during development helps you achieve optimal use of the service.



<a name="loiof0f13bf49e3f45488bcf24218a2771e4__section_nwx_4jp_cjb"/>

## Conventions

-   During the initial pull SAP Task Center loads the tasks, which have been updated or created in the past 90 days \(this is the **maximum initial pull period**\). Previous tasks are not loaded into SAP Task Center.

-   During the initial pull load, if SAP Task Center cannot retrieve a token in one hour, it automatically sets the *tc.enabled* property to ***false***. To continue, you need to manually set the property to ***true***.

-   SAP Task Center communicates with the task provider applications via predefined destinations in a customer subaccount. For each configured destination, SAP Task Center creates a connector to the provider application internally, which updates tasks from this provider into the task cache.

-   For every enabled connector \(with the property ***tc.enabled = true***\), after the initial pull has passed, the task cache is updated with the recently created, modified, or completed tasks as follows:

    -   If the ***tc.clientId*** property is set up for the enabled connector, then the task cache is updated every 5 seconds.

    -   If the ***tc.clientId*** property is not set up for the enabled connector, then the task cache is updated every 30 seconds.

        > ### Note:  
        > Currently the ***tc.clientId*** property is not available for every task provider.


-   A clean-up job runs on a daily basis for every tenant. This job deletes from the task cache the following tasks:

    -   All finalized tasks \(with status *Completed* or *Canceled*\) that have not been updated in the past 1 day

    -   All not-finalized tasks \(for example with status *Ready* or *Reserved*\) that have not been updated in the past 180 days \(this is the **retention period**\)


-   To delete the task cache, you have to temporarily remove the *tc.enabled* property. For more information, see the details for the property *tc.enabled* in the corresponding destination topic \(see [Destinations](../40-administration/destinations-3470733.md)\).

-   To use the SAP Task Center Web app, you need UI5 version 1.108 \(latest patch\) or higher.




<a name="loiof0f13bf49e3f45488bcf24218a2771e4__section_q4p_zk5_ymb"/>

## Technical Restrictions

-   From all supported languages \(see [Supported Languages](supported-languages-c66c693.md)\), SAP Task Center supports simultaneously up to three language translations for tasks and definitions, which are stored in the SAP Task Center service cache. For more information, see [SAP Task Center Global Settings](../40-administration/sap-task-center-global-settings-99e5302.md).

-   The SAP Task Center integration does not support substitutions for any of the supported SAP solutions. If there are defined substitutions or delegates in any of the supported SAP solutions, they will not work with the SAP Task Center.

-   Searching, filtering and sorting by the *Created By* column is not possible.

-   The SAP Task Center service only enables, but does not include the integration implementation from the supported SAP solutions.

-   Not all use cases, supported by the task provider systems, are supported in SAP Task Center. For more information, see [Supported Solutions and Use Cases](supported-solutions-and-use-cases-758209c.md).

-   All messages returned by the SAP Task Center service are only in English.


