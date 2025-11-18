<!-- loiof0f13bf49e3f45488bcf24218a2771e4 -->

# Conventions and Technical Restrictions

These conventions and restrictions apply to the SAP Task Center.

Considering this information during development helps you achieve optimal use of the service.



<a name="loiof0f13bf49e3f45488bcf24218a2771e4__section_nwx_4jp_cjb"/>

## Conventions

-   By default, during the initial pull SAP Task Center loads the tasks, which have been updated or created in the past 90 days \(this is the **maximum initial pull period**\).

    If you are using the `all-tasks` service plan, the retention period of every task provider can be adjusted to a maximum of 180 days by configuring the *tc.inbox.pull.days* property. The allowed values range from 0 to 180. For more information, see the respective task provider destination at [Destinations to Task Providers](../40-administration/destinations-to-task-providers-b158111.md).

-   During the initial pull load, if SAP Task Center cannot retrieve a token in one hour, it automatically sets the *tc.enabled* property to `false`. To continue, you need to manually set the property to `true`.

-   SAP Task Center communicates with the task provider applications via predefined destinations in a customer subaccount. For each configured destination, SAP Task Center creates a connector to the provider application internally, which updates tasks from this provider into the task cache.

-   For every enabled connector \(with the property `tc.enabled = true`\), after the initial pull has passed, the task cache is updated with the recently created, modified, or completed tasks as follows:

    -   If the `tc.clientId` property is set up for the enabled connector, then the task cache is updated upon received information by the task providers.

    -   If the `tc.clientId` property is not set up for the enabled connector, then the task cache is updated every 30 seconds \(the interval may vary\).

        > ### Note:  
        > Currently the `tc.clientId` property is not available for every task provider.


-   A clean-up job runs on a daily basis for every tenant. This job deletes from the task cache the following tasks:

    -   All finalized tasks \(with status *Completed* or *Canceled*\) that have not been updated in the past 1 day. If Outbox is enabled, only canceled tasks are deleted from the task cache.

    -   All completed and non-finalized tasks \(for example with status *Ready* or *Reserved*\) that have not been updated in the past 180 days \(this is the **retention period**\)


-   To delete the task cache, you have to temporarily remove the *tc.enabled* property. For more information, see the details for the property *tc.enabled* in the corresponding destination topic \(see [Destinations](../40-administration/destinations-3470733.md)\).

-   To use the SAP Task Center Web app, you need UI5 version 1.108 \(latest patch\) or higher.

-   The subaccounts of SAP Task Center and the task provider in the SAP BTP, Cloud Foundry environment, must be on the same datacenter.




<a name="loiof0f13bf49e3f45488bcf24218a2771e4__section_q4p_zk5_ymb"/>

## Technical Restrictions

-   From all supported languages \(see [Supported Languages](supported-languages-c66c693.md)\), SAP Task Center supports simultaneously up to three language translations for tasks and definitions, which are stored in the SAP Task Center service cache. For more information, see [SAP Task Center Global Settings](../40-administration/sap-task-center-global-settings-99e5302.md).

-   SAP Task Center supports only substitutions created using SAP Task Center Substitution Management \(see [Substitution Management](../70-using-the-web-app/substitution-management-bef9b2d.md)\). The SAP Task Center integration does not support substitutions created in the supported task providers, except for those created in SAP Build Process Automation. If there are substitutions or delegates, defined in any of the supported SAP or third-party solutions, they will not work with SAP Task Center.

-   Searching, filtering, and sorting by the *Created By* column is not possible.

-   Searching, filtering, and sorting by fields exposing custom attributes with formatted value is not possible, for example custom attributes of type `STRING` and format `USER`, which have formatted value.

-   The SAP Task Center service only enables, but does not include the integration implementation from the supported SAP solutions.

-   Not all use cases, supported by the task provider systems, are supported in SAP Task Center. For more information, see [Supported Solutions and Use Cases](supported-solutions-and-use-cases-758209c.md).

-   All messages returned by the SAP Task Center service are only in English.

-   Notifications displayed in the SAP Task Center Web app are only in English.

    The general restrictions for retention period and total number of notifications are also valid for SAP Task Center. For more information, see [Working with Notifications](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/working-with-notifications).

-   The *Intelligent Recommendations* feature is currently supported only by SAP Build Process Automation and for SAP Build Process Automation tasks.

-   A task can be assigned to two types of recipients \(users and groups\). Each list of recipients \(users and groups\) is restricted by SAP Task Center to 100 members, and only the first 100 users and the first 100 user groups received by SAP Task Center are stored in the task cache.

    Example:

    A task is assigned to 104 users and 125 user groups. This task will be received by the first 100 users and 100 user groups in each list.

-   A task can have multiple recipients but only one single processor. A user is the processor of a task if:

    -   the user is assigned as the single recipient of the task, or
    -   the task is assigned to multiple users as task recipients. One of those recipient users claims the task and becomes its processor. For more information on how to claim a task, see [Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md).

        When a task has a processor, it is visible only in the inbox of its processor. None of the other recipients are able to see the task in their inbox.



