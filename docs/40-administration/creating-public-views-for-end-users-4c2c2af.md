<!-- loio4c2c2af19a5c4bc986d88a957dc502cc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating Public Views for End Users

As a key user, you can create public views with preselected filters that will be available in the end-users' list of views.



<a name="loio4c2c2af19a5c4bc986d88a957dc502cc__section_yjf_f1q_y1c"/>

## Context

As a key user, you can create public views with preselected filters in the SAP Task Center Web app, which will be available and ready for direct application by the end users.

Everyone who has one of the key user roles \(see *Prerequisites*\) can create such public views.

The end users can access the public views from the views dropdown <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span> *My Views* \> *Manage*. For more information on how to work with views, see [Working with Views](../70-using-the-web-app/working-with-views-b446cc8.md).

> ### Note:  
> Currently, users with key user roles can create public views only based on tasks and task types for which they are assigned as processors.



<a name="loio4c2c2af19a5c4bc986d88a957dc502cc__section_g2m_45p_y1c"/>

## Prerequisites

-   You have one of the roles `FlexPublicViewEditor` or `FlexKeyUser`, or both. For more information, see [Creating Public Views](https://help.sap.com/docs/ui5-flexibility-for-key-users/ui5-flexibility-for-key-users/creating-public-views) and [Assign Roles to Your Users](../60-security/assign-roles-to-your-users-7e081d8.md).

-   You have enabled the *Key User Adaptation* setting in the *Services* section of your *Site Settings*. Make sure that you are updating the site, where your SAP Task Center Web app is located. For more information, see [Site Settings](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/configure-site-settings).




<a name="loio4c2c2af19a5c4bc986d88a957dc502cc__section_ntt_kzp_y1c"/>

## Procedure

1.  Open the SAP Task Center Web app.

2.  Make a selection of filter tab, filter, search options, or sorting, which you want to preselect for the end users.

3.  Open the dropdown next to the name of the current view \(<span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span>\) and choose *Save As*.

4.  In the *Save View* window, add the name of the view, choose *Public*, and save it.




<a name="loio4c2c2af19a5c4bc986d88a957dc502cc__section_tsn_d3p_1bc"/>

## Result

The public view is now populated in the *Manage Views* list of the end users. By default, end users do not see the new public view in their *My Views* dropdown list. However, they can set it as default or favorite from their *Manage* menu.

Choosing a public view as a favorite, personalizing it, or making it the default view, will only make it appear in the personal preferences of the key user who created it, but not in the preferences of the end users.

For more information on working with public views, see [Creating Public Views](https://help.sap.com/docs/ui5-flexibility-for-key-users/ui5-flexibility-for-key-users/creating-public-views).

