<!-- loioc8b7aeb8bd02418ea0c26f3ce0d0cf23 -->

# Embed the UI of the SAP Task Center Applications in SAP Build Work Zone or SAP SuccessFactors Work Zone

Embed SAP Task Center applications either in SAP Build Work Zone, standard edition, SAP Build Work Zone, advanced edition, or SAP SuccessFactors Work Zone.



## Prerequisites

-   To embed the SAP Task Center applications, your global account must be located on a public cloud data center.

> ### Restriction:  
> The mobile app does not work if SAP Task Center is embedded in SAP Build Work Zone using a local entry point.



## Procedure

To embed the SAP Task Center Web App and the SAP Task Center Administration App, follow the steps as described in [Auto Discovery Setup](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/auto-discovery-enabled#procedure). As you follow the setup, keep the following details in mind:

-   The business solution to which you need to subscribe to is SAP Task Center. For more information, see [Create a Subscription to the SAP Task Center Service](create-a-subscription-to-the-sap-task-center-service-fd137e3.md).

    > ### Note:  
    > If the subscription was created before February 4, 2026, please delete it and create a new one.

-   When creating the runtime destination, provide the URL of SAP Task Center.

    > ### Note:  
    > The domain uses the following format: `https://{SUBDOMAIN}.one-inbox-lep-sap.{default-domain}`.
    > 
    > You can get the link by opening the SAP Task Center application from the SAP BTP cockpit in *Instances and Subscriptions* and copying it from the search bar or, alternatively, by opening your browser's console and copying it from there.

-   When creating a content channel, select *Subscribed* as *Business Solution Type* and *one-inbox-application* as *Business Solution*.

> ### Note:  
> After creating a content channel, the following role collections are created:
> 
> -   `~<ID>_TaskCenterAdministration` - gives users access to the SAP Task Center Administration App and to the SAP Task Center Web App.
> -   `~<ID>_TaskCenterEveryone` - gives users access to the SAP Task Center Web App.



## Results

You have embedded the SAP Task Center applications in SAP Build Work Zone, standard edition, SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone. End users and administrators can access the embedded SAP Task Center Web App and SAP Task Center Administration App from the SAP Build Work Zone site.

> ### Caution:  
> Administrators can also access the SAP Task Center Web App and SAP Task Center Administration App from their subaccount in the SAP BTP cockpit under *Instances and Subscriptions*. However, do not share the link with end users. The applications from this link are meant to be embedded into a launchpad.



## Next Steps

Continue by connecting your task providers to SAP Task Center. For more information, see [Integrate SAP Task Center with Task Providers](../integrate-sap-task-center-with-task-providers-b158111.md).

