<!-- loio1dfb7505ccba483ba597ba793554096f -->

# Export SAP Task Center Service Data

Export SAP Task Center service data to access business data stored by it.



<a name="loio1dfb7505ccba483ba597ba793554096f__prereq_an2_xqv_qjb"/>

## Prerequisites

-   You have created a Task Center Administration tile, as described in [Create a Task Center Administration Tile](../30-initial-setup/create-a-task-center-administration-tile-8053d72.md).
-   You have the `TaskCenterTenantOperator` role, that allows you to export all data related to tasks and task users. For more information, see [Assign Roles to Your Users](../60-security/assign-roles-to-your-users-7e081d8.md) and [Assign Users to Role Collections](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/c5766765bda74ad59fe656977c8fa4d6.html?version=Cloud).



<a name="loio1dfb7505ccba483ba597ba793554096f__context_mq5_31t_pjb"/>

## Context

You can use this service data to address, for example, audit needs.



<a name="loio1dfb7505ccba483ba597ba793554096f__steps_zbb_ppv_qjb"/>

## Procedure

To export the data, go to the SAP Task Center Administration app. Select the destination whose data you want to export and choose the *Export Cache* button.



<a name="loio1dfb7505ccba483ba597ba793554096f__result_plv_jrv_qjb"/>

## Results

The export call returns a zip file containing the requested data.

> ### Caution:  
> To verify that the export completed successfully, please check that you can extract the zip archive. The archive should not contain a file named `error-log.txt`. If there is an `error-log.txt` file, the exported data might be corrupt. Check the file for details.

