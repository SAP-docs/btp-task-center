<!-- loioe93aa718721444f7aa7e8385a3253a41 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Repopulate the Task Cache

Use the *tc.enabled* property to repopulate tasks and task definitions in the SAP Task Center task cache.



## Context

The tasks and task definitions, fetched from the task provider systems, are stored in the task cache of SAP Task Center. This allows the SAP Task Center Web app and task center in the SAP Mobile Start mobile app to have quick access to the tasks.

If the Outbox feature is enabled, repopulating the task cache will also fetch the completed tasks from the task provider systems and will store them in the task cache of SAP Task Center. To enable Outbox, see [SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md).

To delete and repopulate the task cache for a destination \(see [Destinations](destinations-3470733.md)\), you have to remove the *tc.enabled* property for this destination and add it again in a few minutes.



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Connectivity* \> ***Destinations* tab from the navigation area.

2.  Open the destination configuration of the task provier, for which you want to repopulate the task cache and verify that the *tc.enabled* property is enabled.

3.  Open the Task Center Administration app \(see [Working with the Task Center Administration App](working-with-the-task-center-administration-app-3a1598c.md)\) and verify that the connector to this destination is listed below the destinations.

4.  Go back to the destination configuration in your Cloud Foundry subacount and switch to edit mode. Search for *tc.enabled* below *Additional Properties*, and remove the property \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\). Save your changes.

5.  Go back to the Task Center Administration app and wait until the connector to the destination is not present anymore.

6.  Back in your Cloud Foundry subaccount, open the destination configuration in edit mode, choose *New Property* and add *tc.enabled* with value `true`. Save the configuration. This allows the jobs in the background to fetch all tasks and task definitions from the task provider system.

7.  The destination connector should be present again in the Task Center Administration app. Make sure that the *INITIAL* job is there, and the *CONFIG* job is with status *OK* .




<a name="loioe93aa718721444f7aa7e8385a3253a41__result_tq4_brw_d5b"/>

## Results

The task cache is now repopulated for this destination. You should receive all tasks from this destination that have been updated or created during the maximum initial pull period. For more information about the maximum initial pull period, see [Conventions and Technical Restrictions](../10-what-is/conventions-and-technical-restrictions-f0f13bf.md).

