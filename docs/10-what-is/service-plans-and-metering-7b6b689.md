<!-- loio7b6b6898251f449a978fffdb27cc5e50 -->

# Service Plans and Metering

This page explains the relationship between the service plans in the SAP Discovery Center and those in the SAP BTP cockpit, and provides information to help you understand how SAP Task Center is billed.



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_gwp_yyy_5zb"/>

## Service Overview

The following commercial models are available for SAP Task Center:

-   Consumption-based commercial model

-   Subscription-based commercial model


For more information, see [Commercial Models](https://help.sap.com/docs/btp/sap-business-technology-platform/commercial-models).

![](images/Consumption-Based_Models_STC_e56c6f4.png)

\* For more information on the SAP Build Work Zone SKUs, see [SAP Build Work Zone, standard edition - Service Plans and Metering](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/commercial-models-and-metering) and [SAP Build Work Zone, advanced edition - Service Plans and Metering](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/commercial-models-and-metering).

![](images/Subscriptions_STC_pptx_8f54345.png)

\* For more information on the SAP Build `build-default` service plan, see [Service Plans and Metering](https://help.sap.com/docs/build-service/build-service-guide/service-plans-and-metering).



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_hbp_bwc_w1c"/>

## Service Plans



### SAP BTP Cockpit: Service Plans

The information about the service plans is valid for both the consumption-based and subscription-based commercial models, except for the highlighted commercial-model-specific information.


<table>
<tr>
<th valign="top">

Name in SAP BTP Cockpit 

</th>
<th valign="top">

Service Plan in SAP Discovery Center

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`cloud-only-tasks`

</td>
<td valign="top">

*Cloud-Only Tasks*

</td>
<td valign="top">

To be used only with SAP Start.

The SAP Task Center free *Cloud-Only Tasks* service plan enables the integration of SAP Task Center with the supported SAP cloud solutions.

This service plan must be used only for the SAP Start use case \(in conjunction with the SAP Build Work Zone foundation service plan\). For more information, see [SAP Start - Service Plans and Metering](https://help.sap.com/docs/start/sap-start/availability).

Users are allowed to use for free up to 20 tasks \(2 blocks of 10 records\) stored in the SAP Task Center task cache for each active user on global account level. This is valid for up to 1 000 active users per month.

All tasks above this number are charged and you will be requested to use the consumption-based commercial model, `all-tasks` service plan.

</td>
</tr>
<tr>
<td valign="top">

`all-tasks`

</td>
<td valign="top">

*All Tasks*

</td>
<td valign="top">

The SAP Task Center *All Tasks* plan enables the integration of SAP Task Center with all supported SAP cloud, SAP S/4HANA on-premise, and third-party task providers.

This service plan must be used with the SAP Build Work Zone, standard edition; SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone service plans. For more information, see [SAP Build Work Zone, standard edition - Service Plans and Metering](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/commercial-models-and-metering) and [SAP Build Work Zone, advanced edition - Service Plans and Metering](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/commercial-models-and-metering).

Users are allowed to use for free up to 20 tasks \(2 blocks of 10 records\) stored in the SAP Task Center task cache for each active user, and for each block of 100 SAP Build Work Zone connections on global account level.

> ### Note:  
> For the subscription-based commercial model:
> 
> -   All tasks above those 20 tasks are charged and you will be requested to use the consumption-based commercial model, `all-tasks` service plan.
> 
>     In this case you'll also need a SAP BTPEA \(SAP BTP Enterprise Agreement\) license. For more information, see [What Is the Consumption-Based Commercial Model?](https://help.sap.com/docs/btp/sap-business-technology-platform/what-is-consumption-based-commercial-model).
> 
> -   On a global account level all licensed users are considered as active users



</td>
</tr>
<tr>
<td valign="top">

`build-default`

</td>
<td valign="top">

*Build Default*

</td>
<td valign="top">

Availabe with SAP-BUILD subscription only.

The SAP Task Center *Build Default* plan enables the integration of SAP Task Center with all supported SAP cloud, SAP S/4HANA on-premise, and third-party task providers.

This service plan must be used with SAP Build Work Zone, standard edition; SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone service plans. For more information, see [SAP Build Work Zone, standard edition - Service Plans and Metering](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/commercial-models-and-metering) and [SAP Build Work Zone, advanced edition - Service Plans and Metering](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/commercial-models-and-metering).

Users are allowed to use for free up to 20 tasks \(2 blocks of 10 records\) stored in the SAP Task Center task cache for each active user, and for each block of 100 SAP Build Work Zone connections on global account level.

> ### Note:  
> For the subscription-based commercial model:
> 
> -   All tasks above those 20 tasks are charged and you will be requested to use the consumption-based commercial model, `all-tasks` service plan.
> 
>     In this case you'll also need a SAP BTPEA \(SAP BTP Enterprise Agreement\) license. For more information, see [What Is the Consumption-Based Commercial Model?](https://help.sap.com/docs/btp/sap-business-technology-platform/what-is-consumption-based-commercial-model).
> 
> -   On a global account level all licensed users are considered as active users



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

`standard`

</td>
<td valign="top">

*Standard*

</td>
<td valign="top">

This service plan is scheduled to be removed from the list of Eligible Cloud Services as of November 15. It will be available until the end of the current subscription term. It will not be available for renewal terms that begin after the removal date. You can use the *All Tasks* or *Build Default* service plans, which now include the features of the *Standard* service plan, or the *Cloud-Only Tasks* service plan if you want to integrate with the supported SAP cloud solutions.

</td>
</tr>
<tr>
<td valign="top">

*On-Premise and Third-Party*

</td>
<td valign="top">

This service plan is scheduled to be removed from the list of Eligible Cloud Services as of November 15. It will be available until the end of the current subscription term. It will not be available for renewal terms that begin after the removal date. You can use the *All Tasks* or *Build Default* service plans, which now include the features of the *On-Premise and Third-Party* service plan, or the *Cloud-Only Tasks* service plan if you want to integrate with the supported SAP cloud solutions.

</td>
</tr>
</table>

For more information on the SAP Task Center availability and service plans, see [SAP Task Center Service Plans on SAP Discovery Center](https://discovery-center.cloud.sap/protected/index.html#/serviceCatalog/sap-task-center?tab=service_plan&region=all).



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_x43_x1z_5zb"/>

## Metrics


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Definition

</th>
</tr>
<tr>
<td valign="top">

Records in Blocks of 10

</td>
<td valign="top">

The Usage Metric for the Cloud Service is Record. For this Cloud Service, tasks are counted.

</td>
</tr>
<tr>
<td valign="top">

Tasks in Blocks of 1 000

</td>
<td valign="top">

\(This metric is only for the *Standard* service plan.\)

Individual, structured data objects that are managed via the Cloud Service, such as characters, objects, tasks, and jobs.

For the Cloud Service, a record is a line-item in the input to the reconciliation process.

</td>
</tr>
</table>

Records with the service plan *All Tasks* are tasks, stored in the SAP Task Center task cache and are counted only for users who have used SAP Task Center at least once in the past 30 days. This defines the number of active SAP Task Center users. This count includes tasks in both the SAP Task Center *Inbox* and *Outbox*.

Please keep in mind that the tasks are kept in the SAP Task Center task cache for 180 days \(retention period\).



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_o4b_bsz_5zb"/>

## Backward Calculation



### Formula

You can have multiple instances of SAP Task Center in the same sub account with different service plans, but only one active service plan. The active service plan for a subaccount is:

-   `build-default`, if there is at least one SAP Task Center instance with the `build-default` service plan.
-   `all-tasks`, if there is no instance with the `build-default` service plan and at least one instance with the `all-tasks` service plan.
-   `cloud-only-tasks`, if there is no instance with the `build-default` or `all-tasks` service plan, and at least one instance with the `cloud-only-tasks` service plan.
-   `standard`, if all instances are only with plan `standard`.



### Examples

> ### Example:  
> **Example 1:** You have a subaccount which contains SAP Task Center instances with the following plans:
> 
> -   `standard`
> -   `cloud-only-tasks`
> 
> The effective service plan is `cloud-only-tasks`. Only cloud tasks are allowed.

> ### Example:  
> **Example 2:** You have a subaccount which contains SAP Task Center instances with the following plans:
> 
> -   `standard`
> -   `cloud-only-tasks`
> -   `all-tasks`
> 
> The effective service plan is `all-tasks`. Cloud, on-premise and third-party tasks are allowed.

> ### Example:  
> **Example 3:** You have a subaccount which contains SAP Task Center instances with the following plans:
> 
> -   `standard`
> -   `all-tasks`
> 
> The effective service plan is `all-tasks`. Cloud, on-premise, and third-party tasks are allowed.

> ### Example:  
> **Example 4:** You have a subaccount which contains SAP Task Center instances with the following plans:
> 
> -   `build-default`
> -   `all-tasks`
> 
> The effective service plan is `build-default`. Cloud, on-premise, and third-party tasks are allowed.



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_avt_bvp_hfc"/>

## Migrating to a Different SAP Task Center Service Plan

If you're planning to switch from one SAP Task Center service plan to another, here's what you need to know:



### Service Plans Ranking

SAP Task Center offers the following service plans, which are ordered by priority:

1.  `build-default`
2.  `all-tasks`
3.  `cloud-only-tasks`
4.  `standard`

This ranking means that if your subaccount has multiple service instances with different service plans, the service instance with the highest-ranking plan in the list is the active one. For example, if you have a `build-default` plan, it takes priority over the other service plans.

In the case of multiple SAP Task Center instances in a single subaccount, only the instance with the highest-ranking plan will be active, but configuration from non-active service instances might still be used by SAP Task Center.



### How to Migrate to Another Service Plan

If you want to migrate from one SAP Task Center service plan to another, you must have in mind the service plans ranking.

To migrate from a lower-ranking to a higher-ranking service plan \(for example, from `standard` to `all-tasks`, proceed as follows:

1.  Navigate to your Cloud Foundry subaccount which contains an instance of the SAP Task Center lower-ranking service plan \(for example, `standard`\).
2.  In the same subaccount create a new service instance with the higher-ranking service plan \(for example, `all-tasks`\).

    For more information on how to create a new service instance, see [Create a Service Instance Using the SAP BTP Cockpit](../30-initial-setup/create-a-service-instance-using-the-sap-btp-cockpit-dc9af9f.md).


If you need support to migrate from a higher-ranking to a lower-ranking service plan \(for example, from `all-tasks` to `cloud-only-tasks`\), create a ticket to the SAP Task Center component as described in [Troubleshooting](../80-troubleshooting/troubleshooting-89c09a4.md).

> ### Caution:  
> Removal of existing service instances on which you have set up SAP Task Center might lead to loss of data or SAP Task Center configurations.



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_mjy_gbz_5zb"/>

## Supplemental Terms and Conditions

For more information, see the [SAP Business Technology Platform Service Description Guide](https://www.sap.com/about/trust-center/agreements/cloud/cloud-services.html?sort=latest_desc&tag=language%3Aenglish&pdf-asset=82ce6fed-917e-0010-bca6-c68f7e60039b&page=1), *SAP TASK CENTER* section.



<a name="loio7b6b6898251f449a978fffdb27cc5e50__section_bl4_4tz_5zb"/>

## Glossary

[Commercial Information Glossary](https://help.sap.com/docs/help/5d771150f8f547c6bc604c7d674cf30d/7014f9db099148f1897c1bda5db21f39.html)

