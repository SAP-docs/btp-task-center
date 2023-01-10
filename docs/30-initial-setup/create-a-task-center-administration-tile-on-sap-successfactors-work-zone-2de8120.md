<!-- loio2de8120b02c342d5b0edf57e4d6004da -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Administration Tile on SAP SuccessFactors Work Zone

Create a Task Center Administration tile in the SAP SuccessFactors Work Zone to monitor the status of all active destinations and get information about their jobs and job types.



<a name="loio2de8120b02c342d5b0edf57e4d6004da__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

-   You have a subscription to SAP SuccessFactors Work Zone in your subaccount, and you have the `HR_Workflow_Admin` role collection assigned to your user. For more information, see [Onboarding to SAP SuccessFactors Work Zone](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/edc62f97f50a432bb8dba04626689050.html).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loio2de8120b02c342d5b0edf57e4d6004da__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center Administration tile in SAP SuccessFactors Work Zone. The Task Center Administration app displays the status of all active destinations, information about their jobs and job types. For more information about the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).



<a name="loio2de8120b02c342d5b0edf57e4d6004da__steps_dkx_pkx_sqb"/>

## Procedure

1.  Build your own *Content Manager* link, as described in *Accessing the Site Manager* in [Site Manager in a Nutshell](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/1589c253001a4433980ada7fa94df8d0.html). Make sure you use the type for SAP SuccessFactors Work Zone, as described in [Solution Architecture and Authentication Details](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/1fd9ea4f7051499db52b2dc086b86b54.html#hostname-pattern). Open the link.

2.  In the new window, go to *Channel Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *HTML 5 Apps* and choose *Update content*\( <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) below *Actions* to fetch the updated content.

3.  Go to *Content Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *Content Explorer* tab, choose *HTML5 Apps*, select the Task Center Administration item and choose *\+ Add to My Content*.

4.  Go to the *My Content* tab where the Task Center Administration app is added.

5.  Choose *\+ New* \> *Group*.

6.  Add a group title, assign the Task Center Administration app from the *Assignments* section, and save your changes.

7.  Create a new role, for example *Administrator*, and assign Task Center Administration to it.

8.  Go to the *Site Directory* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) and create a new site \(*\+ Create Site*\).

9.  Make sure you assign the new role to the new site and assign administrators to the role collection in the SAP BTP cockpit.

10. From the *Site Editor* open the site \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). The Task Center Administration tile is available now.




<a name="loio2de8120b02c342d5b0edf57e4d6004da__result_h3j_4ss_tnb"/>

## Results

The integration of the Task Center Administration app in the SAP SuccessFactors Work Zone is done and the Task Center Administration tile is available. For more information about the details provided by the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).

