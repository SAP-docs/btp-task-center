<!-- loio494aa0c59c0d44f8ba701134ae4d9e3f -->

# SAP Task Center Service Destinations

Set up the service destinations, required for some of the SAP Task Center features.



## Create the Service Destinations

The service destinations are additional destinations created in the SAP BTP cockpit or an additional setup in the SAP Task Center Administration application. Setting up these destinations give you and the end users the following functionalities:

**Service Destinations**


<table>
<tr>
<th valign="top">

Service Destinaiton

</th>
<th valign="top">

Description

</th>
<th valign="top">

How to Set It Up

</th>
</tr>
<tr>
<td valign="top">

*Task\_Center* 

</td>
<td valign="top">

This destination is created automatically by the booster, or you can set it up manually for the central point of entry for accessing applications. It is a mandatory destination, but there should be only one *Task\_Center* destination per service instance.

> ### Note:  
> If you have followed the [Automatic Setup](automatic-setup-3a49967.md), this destination is already created by the booster. Please do not change this destination, and do not create a second destination for the central point of entry for accessing applications.



</td>
<td valign="top">

[Destination for the Central Point of Entry for Accessing Applications](destination-for-the-central-point-of-entry-for-accessing-applications-10320af.md)

</td>
</tr>
<tr>
<td valign="top">

*Task\_Center\_global\_settings*

</td>
<td valign="top">

This destination contains the preffered language settings, valid for all task providers, as well as the *Outbox* preferences and others. The settings in this destination are valid for all task providers.

</td>
<td valign="top">

[SAP Task Center Global Settings](sap-task-center-global-settings-99e5302.md)

</td>
</tr>
<tr>
<td valign="top">

*Identity\_Authentication\_Connectivity\_IDS*

</td>
<td valign="top">

This destination establishes the connection to the identity directory of Identity Authentication, this is information about the users and their user details. This informaion is used, for example, when searching for users when creating a substitution.

</td>
<td valign="top">

[Identity Directory Connectivity](identity-directory-connectivity-3dcfba9.md)

</td>
</tr>
<tr>
<td valign="top">

*Alert\_Notification\_Connectivity\_ANS*

</td>
<td valign="top">

This destination must be configured as part of the setup, enabling notifications for end users.

</td>
<td valign="top">

[Alert Notifications Connectivity](alert-notifications-connectivity-f6c9f3b.md)

</td>
</tr>
</table>

> ### Note:  
> Do not set the *tc.enabled* property in these service destinations.



## Next Steps

Once you have completed the service destination setup, you can continue with setting up the task provider destinations. For more information, see [Integrate SAP Task Center with Task Providers](../integrate-sap-task-center-with-task-providers-b158111.md).

