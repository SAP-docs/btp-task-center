<!-- loioe64ec036977344b18aa9d8fababb178d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Administration Tile on SAP Build Work Zone, advanced edition

Create a Task Center Administration tile in SAP Build Work Zone, advanced edition to monitor the status of all active destinations and get information about their jobs and job types.



<a name="loioe64ec036977344b18aa9d8fababb178d__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

-   You have a subscription to SAP Build Work Zone, advanced edition in your subaccount, and you have the `Workzone_Admin` role collection assigned to your user. For more information, see [What Is SAP Build Work Zone, Advanced Edition](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/5c0103b130de411fb2a4b5416e36d767.html).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loioe64ec036977344b18aa9d8fababb178d__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center Administration tile in SAP Build Work Zone, advanced edition. The Task Center Administration app displays the status of all active destinations, information about their jobs and job types. For more information about the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).



<a name="loioe64ec036977344b18aa9d8fababb178d__steps_dkx_pkx_sqb"/>

## Procedure

1.  Build your own *Site Directory* link, as described in *Accessing the Site Manager* in [Site Manager in a Nutshell](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/1589c253001a4433980ada7fa94df8d0.html) and open the link.

2.  In the new window, go to *Channel Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *HTML 5 Apps* and choose *Update content*\( <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) below *Actions* to fetch the updated content.

3.  Go to *Content Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *Content Explorer* tab, choose *HTML5 Apps*, select the Task Center Administration item and choose *\+ Add to My Content*.

4.  Go to the *My Content* tab where the Task Center Administration app is added.

5.  Choose *\+ New* \> *Group*.

6.  Add a group title, assign the Task Center Administration app from the *Assignments* section, and save your changes.

7.  Create a new role, for example *Administrator*, and assign the Task Center Administration to it.

    For more information, see [Assign Apps to Roles](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/d0842269a2bd4b97a47ac19082e286a5.html).

8.  Go to *Site Directory* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) and choose *Open Site* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). The Task Center Administration tile is available below *Applications*.

9.  Make sure you assign administrators to the new role collection in the SAP BTP cockpit.




<a name="loioe64ec036977344b18aa9d8fababb178d__result_h3j_4ss_tnb"/>

## Results

The integration of the Task Center Administration app in SAP Build Work Zone, advanced edition is done and the Task Center Administration tile is available. For more information about the details provided by the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).

