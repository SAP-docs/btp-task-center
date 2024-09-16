<!-- loio99e53020ef7441cda1e72f843404fa5f -->

# SAP Task Center Global Settings

Configure the *Task\_Center\_global\_settings* destination, to set the properties valid for all destinations.



<a name="loio99e53020ef7441cda1e72f843404fa5f__context_jmy_gbr_szb"/>

## Context

> ### Note:  
> Notifications displayed in the SAP Task Center Web app are only in English.



## Procedure

1.  Navigate to the Cloud Foundry subaccount, where your SAP Task Center instance was created, and select the *Destinations* tab from the navigation area.

2.  If you have executed the automatic setup \(see [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md)\), you have an already created destination with the name *Task\_Center\_global\_settings*. Configure the properties as described next.

    If you have followed the manual setup \(see [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md)\), you have to create a new destination and manually add the properties as described next.

3.  Configure the properties of the destination as described in the following table:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Example or Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Task\_Center\_global\_settings
    
    </td>
    <td valign="top">
    
    **Value**:

    `Task_Center_global_settings`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Choose the *HTTP* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    \(Optional\) Add a description as a free text.
    
    </td>
    <td valign="top">
    
    `SAP Task Center Global Settings`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    Add `http://sap.com/` as value.
    
    </td>
    <td valign="top">
    
    **Value**:

    `http://sap.com/`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
    </td>
    <td valign="top">
    
    Choose the *Internet* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    Choose the *NoAuthentication* option from the dropdown menu.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
    Additional Properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Example or Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.languages*
    
    </td>
    <td valign="top">
    
    List of translation languages to be requested for the translatable fields. For more information, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

    The number of languages configured must be between one and three. If this count is exceeded, SAP Task Center uses only the first three languages from the list and ignores the rest of the language codes.

    We recommend you to set en-US as one of these three languages, as translations in this language are usually present for the supported SAP task providers.

    If you change the configured languages, you have to repopulate the task cache by disabling and enabling the *tc.enabled* property for every destination. For more information, see [Repopulate the Task Cache](repopulate-the-task-cache-e93aa71.md).

    > ### Note:  
    > SAP Task Center uses en-US as a fallback language, if there is no *Task\_Center\_global\_settings* destination configured, or its name is misspelled, or the language codes are not supported.
    > 
    > If any language code is invalid or unsupported, SAP Task Center ignores these language codes and uses only the correct ones.


    
    </td>
    <td valign="top">
    
    **Example**:

    `en-US,de-DE`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *tc.wz.home.url*
    
    </td>
    <td valign="top">
    
    This property defines the root URL of SAP Task Center in SAP Build Work Zone. It is required for the email notifications from SAP Task Center.
    
    </td>
    <td valign="top">
    
    `https://sample.com/site?siteId=1234abcd-12ab-12ab-12ab-123456abcdef#taskcenter-display`
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.


