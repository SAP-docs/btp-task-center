<!-- loiocaf254347efa4ce09d749c6a3e2bff8e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable Notifications for End Users

Enable notifications for end users, ensuring that they receive timely task alerts.



<a name="loiocaf254347efa4ce09d749c6a3e2bff8e__prereq_e2b_w4w_tyb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).

-   You have set up the *Identity\_Authentication\_Connectivity\_IDS* destination. For more information, see [Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md).

-   You are using SAP Build Work Zone, standard edition or SAP Build Work Zone, advanced edition as a central point of entry for accessing applications.




<a name="loiocaf254347efa4ce09d749c6a3e2bff8e__section_gmr_dqg_vyb"/>

## Context

Administrators can set up notifications for the end users to be informed upon receiving a new task in their task list \(task assignment\). Currently, the notifications displayed in the SAP Task Center Web app and task center in the SAP Mobile Start mobile app are in English. However, they might contain information in the fallback language, defined by the task provider. For more information on the fallback language, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

Notifications for substitutions or changes in processors are currently not supported.

To enable notifications for all or only some of the connected task providers, follow the steps in the procedure.



## Procedure

1.  Open your central point of entry for accessing applications.

    -   If your central point of entry for accessing applications is SAP Build Work Zone, standard edition, follow the steps in [Enabling Notifications from Cloud Solutions and Services](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/enabling-notifications-from-cloud-solutions).

    -   If your central point of entry for accessing applications is SAP Build Work Zone, advanced edition, follow the steps in [Enabling Notifications from Cloud Solutions and Services](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/enabling-notifications-from-cloud-solutions).


    Make sure you complete the following steps:

    -   Choose *Email* as authentication identifier.

    -   Generate credentials in the subaccount settings screen.

        These credentials are used for the connection between SAP Task Center and your central point of entry for accessing applications \(see [Alert Notifications Connectivity](alert-notifications-connectivity-f6c9f3b.md)\).

    -   Enable the display of notifications in the *Site Settings* \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) screen.

    -   Select the notifications \(done by end users after the notifications setup is completed\).


2.  Create a destination for the connection to the notification service, as described in [Alert Notifications Connectivity](alert-notifications-connectivity-f6c9f3b.md).

3.  Set the *tc.notifications.enabled* property in the destination of every task provider, for which you want to enable notifications. For more info, see the respective task provider topic in [Destinations to Task Providers](destinations-to-task-providers-b158111.md).

4.  \(Optional\) Enable email notifications for end users.

    To offer email notifications to the end users, you must have completed the previous steps in this topic, then continue as follows:

    1.  Configure a destination to the mail server, as described in [Configuring an SMTP Mail Destination](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/configuring-smtp-mail-destination).

    2.  Set the *tc.wz.home.url* property in the *Task\_Center\_global\_settings* destination. For more information, see [SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md).
    3.  Make sure to inform the end users to update their notification settings individually in their *SAP Task Center Web app* \> *User Menu* \> *Settings* \> *Notifications* \> *Emails* section, and select the task types they want to receive email notifications for.

        By default the email notifications are disabled.





<a name="loiocaf254347efa4ce09d749c6a3e2bff8e__result_fkz_zrw_tyb"/>

## Results

The notifications are now enabled for end users. For more information, see [Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md).

**Related Information**  


[Developing Cloud Foundry Applications With Notifications](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/developing-cloud-foundry-applications-with-notifications)

[Enabling Notifications From Cloud Solutions and Services \(SAP Build Work Zone, standard edition\)](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/enabling-notifications-from-cloud-solutions)

[Enabling Notifications From Cloud Solutions and Services \(SAP Build Work Zone, advanced edition\)](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/enabling-notifications-from-cloud-solutions)

