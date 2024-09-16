<!-- loiocaf254347efa4ce09d749c6a3e2bff8e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable Notifications for End Users

Enable notifications for end users, ensuring that they receive timely task alerts.



<a name="loiocaf254347efa4ce09d749c6a3e2bff8e__prereq_e2b_w4w_tyb"/>

## Prerequisites

-   You have completed the initial setup of SAP Task Center. For more information, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).

-   You have set up the *Identity\_Authentication\_Connectivity\_IDS* destination. For more information, see [Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md).

-   You are using the SAP Task Center Web app on SAP Build Work Zone, standard edition.




<a name="loiocaf254347efa4ce09d749c6a3e2bff8e__section_gmr_dqg_vyb"/>

## Context

Administrators can set up notifications for the end users to be informed upon receiving a new task in their task list \(task assignment\). Currently, the notifications displayed in the SAP Task Center Web app and task center in the SAP Mobile Start mobile app are in English, but might contain information in the fallback language, defined by the task provider. For more information on the fallback language, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

Notifications for substitutions or changes in processors are currently not supported.

To enable notifications for all or only some of the connected task providers, follow the steps in the procedure.



## Procedure

1.  Open SAP Build Work Zone, standard edition.

    For more information, see [What Is SAP Build Work Zone, standard edition?](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/what-is-sap-build-work-zone-standard-edition).

2.  From the *Site Directory* \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\) open the *Site Settings* \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) of the site, where you created your Task Center tile.

3.  Choose *Edit*, enable the *Show Notifications* setting under the *Display* section and save your changes. For more information, see the subtopics in [Enabling Notifications](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/enabling-notifications).

4.  From the main screen of SAP Build Work Zone, standard edition, open <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Settings* and go to the *Notifications* tab. To access this tab, you need the relevant notification roles, as described in [Subaccount Settings](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/subaccount-settings).

5.  Set *Email* as authentication identifier.

6.  Choose *Generate* and note down the values of the following properties in the *Generate Credentials* section:

    -   *Host*
    -   *OAuth 2.0 Client ID*
    -   *Client Secret*
    -   *Token Endpoint*

    > ### Note:  
    > If you regenerate these credentials, you must update them in the notifications destination, created in the next step.

7.  Create a destination for the connection to the notification service, as described in [Alert Notifications Connectivity](alert-notifications-connectivity-f6c9f3b.md).

8.  Set the *tc.notifications.enabled* property in the destination of every task provider, for which you want to enable notifications. For more info, see the respective task provider topic in [Destinations to Task Providers](destinations-to-task-providers-b158111.md).

9.  \(Optional\) Enable email notifications for end users.

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

