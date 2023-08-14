<!-- loio55fc2c0b94f04f5d877352958acd17b6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Task Center Administration Tile on SAP Build Work Zone, standard edition

Create a Task Center Administration tile in the SAP Build Work Zone, standard edition \(formerly known as SAP Launchpad service\) to monitor the status of all active destinations and get information about their jobs and job types.



<a name="loio55fc2c0b94f04f5d877352958acd17b6__prereq_u4n_mbc_d3b"/>

## Prerequisites

-   You have created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service](create-a-service-instance-of-the-sap-task-center-service-d36035e.md).

-   You have a subscription to SAP Build Work Zone, standard edition in your subaccount, and you have the `Launchpad_Admin` role collection assigned to your user. For more information, see [Initial Setup](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/fd79b232967545569d1ae4d8f691016b.html).

-   You have the `TaskCenterAdmin` role. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loio55fc2c0b94f04f5d877352958acd17b6__context_bn4_nc3_j3b"/>

## Context

The following procedure describes how to create a Task Center Administration tile in the SAP Build Work Zone, standard edition. The Task Center Administration app displays the status of all active destinations, information about their jobs and job types. For more information about the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).

> ### Note:  
> If you are already using SAP Cloud Portal service, you can continue with step 2 and replace *Launchpad service* by *Cloud Portal Service*. For more information about the SAP Cloud Portal service, see [SAP Cloud Portal Service](https://help.sap.com/viewer/product/Portal_Service/1.0/en-US).



<a name="loio55fc2c0b94f04f5d877352958acd17b6__steps_dkx_pkx_sqb"/>

## Procedure

1.  In the navigation menu of the SAP BTP cockpit in your subaccount, choose *Instances and Subscriptions*.

2.  In the *Subscriptions* section, search for the *Launchpad Service* and choose *Go to Application* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\).

3.  In the new window, go to *Channel Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *HTML 5 Apps* and choose *Update content*\( <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) below *Actions* to fetch the updated content.

4.  Go to *Content Manager \(*<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>*\)* \> *Content Explorer* tab, choose *HTML5 Apps*, select the Task Center Administration item and choose *\+ Add to My Content*.

5.  Go to the *My Content* tab where the Task Center Administration app is added.

6.  Choose *\+ New* \> *Group*.

7.  Add a group title, assign the Task Center Administration app from the *Assignments* section, and save your changes.

8.  Create a new role, for example *Administrator*, and assign the Task Center Administration to it.

    For more information, see [Assign Content to a Role](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/baeaf6ee364e48ac95dc09470281f174.html).

9.  Go to the *Site Directory* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\) and create a new site \(*\+ Create Site*\). For more information, see [Create a Site](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/5778444e0419462bb4060a66a5c20de0.html).

10. Make sure you assign the new role to the new site and assign administrators to the role collection in the SAP BTP cockpit. For more information, see [Assign Roles to a Site](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/13e9abe196604356bb28bc2743e78ae9.html).

11. From the *Site Editor* open the site \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons"></span></span></span>\). The Task Center Administration tile is available now.




<a name="loio55fc2c0b94f04f5d877352958acd17b6__result_h3j_4ss_tnb"/>

## Results

The integration of the Task Center Administration app in the SAP Build Work Zone, standard edition is done and the Task Center Administration tile is available. For more information about the details provided by the Task Center Administration app, see [Working with the Task Center Administration App](../40-administration/working-with-the-task-center-administration-app-3a1598c.md).

