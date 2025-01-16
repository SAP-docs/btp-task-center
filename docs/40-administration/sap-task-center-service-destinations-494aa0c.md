<!-- loio494aa0c59c0d44f8ba701134ae4d9e3f -->

# SAP Task Center Service Destinations

Set up the service destinations, required for some of the SAP Task Center features.

> ### Note:  
> Do not set the *tc.enabled* property in these service destinations.

-   To configure the destination for the connection to the central point of entry for accessing applications, see [Destination for the Central Point of Entry for Accessing Applications](destination-for-the-central-point-of-entry-for-accessing-applications-10320af.md).

    > ### Note:  
    > If you have followed the [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md), this destination is already created by the booster. Please do not change this destination, and do not create a second destination for the central point of entry for accessing applications.

-   To configure the global settings, valid for all task provider destinations, see [SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md).
-   To configure connection to the identity directory of Identity Authentication, and retrieve the required information about the end users, valid for all task provider destinations, see [Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md) \(mTLS communication supported\).
-   To configure the destination required for the enablement of notifications for end users, see [Alert Notifications Connectivity](alert-notifications-connectivity-f6c9f3b.md).

