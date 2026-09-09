<!-- loiobef9b2d6ec6a4c6f858e936fcdf9a4c5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Substitution Management

Use *Substitution Management* to access and maintain your substitutions.

When planning your absence, you can add substitution rules in the SAP Task Center Web app, so that your substitute can work on your tasks, displayed directly in their Web app, for the period that you define.

Open the *Substitution Management* tab from the header bar of your SAP Task Center Web app.

For more information about the task providers that support *Substitution Management*, see [Supported Features](../10-what-is/supported-features-257a0ad.md).

> ### Note:  
> -   SAP Task Center works only with substitutions created in the *Substitution Management* of SAP Task Center. Substitutions created in the task providers are not supported, except for those created in My Inbox in SAP Build Process Automation.
> 
>     Note that substitutions created in My Inbox in SAP Build Process Automation may have a shift in start and end dates by one day due to the user's time zone. If you have any doubts, check the original substitution rule in My Inbox in SAP Build Process Automation.
> 
> -   Business administrators can use the substitution management feature in the Task Center Administration app and create or manage substitution rules on behalf of end users. For more information, see [Substitution Management for Business Administrators](../40-administration/substitution-management-for-business-administrators-3adfedc.md).



<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_hts_1wb_svb"/>

## Prerequisites

-   To access the *Substitution Management* option in the SAP Task Center Web app, there must be at least one active task provider that supports substitutions. Otherwise, the *Substitution Management* option is not available in the header bar.

-   To create a substitution for a specific task provider, this task provider must support substitutions.




<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_g5r_fyb_svb"/>

## Substitution Management View

The *Substitution Management* view consists of the following areas:

-   *Substitutions*

    Contains substitutions, added by you. Choose a rule from this list to see more details about it in the details area.

    A substitution can have the following status:

    -   *Ongoing*

    -   *Ongoing \(Not Active\)*

    -   *Upcoming*


    The status of the substitutions is also color-coded as follows:

    -   Green: No errors \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\)

    -   Orange: Needs your attention. There is at least one error in this substitution \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

    -   Gray: Upcoming substitution without errors


-   *Details*

    In the details area you can find more information about the substitution, its scope, and a calendar displaying the substitution period.

    In the *Scope* table you can see in which task providers the substitution is created, its status for the specific task provider system, and optionally an action button. A substitution can have the following status:

    -   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors, but with a message you should review.

    -   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors.

    -   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *ERROR* for substitutions with errors, that you can repair from the *Action* column.



Currently you can only view the details of a created substitution, but cannot edit it.



<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_Search"/>

## Substitution By and Substitution For

The tabs above the first column allow you to view the existing substitutions.



### *Substituted By* Tab

Choose the *Substituted By* tab to search for substitution rules, where the user you are searching for has the role of substituted user.


<table>
<tr>
<th valign="top">

Substitutions List

</th>
<th valign="top">

Substitution Details

</th>
</tr>
<tr>
<td valign="top">

The substitution list in the *Substituted By* tab contains substitution rules, where the user you are searching for has the role of substituted user. The substitution is named after the substitute.

Choose a rule from this list to see more details about it in the details area.

A substitution can have the following status:

-   *Ongoing*

-   *Ongoing \(Not Active\)*

-   *Upcoming*


The status of the substitutions is also color-coded as follows:

-   Green: No errors \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\)

-   Orange: Needs your attention. There is at least one error in this substitution \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

-   Gray: Upcoming substitution without errors, or inactive unexpected substitutions.




</td>
<td valign="top">

In the *Substituted By* view you can find more information about the substituted user, the scope of the substitution, and a calendar displaying the substitution period.

In the *Scope* table you can see in which task providers the substitution is created, its status for the specific task provider system, and optionally an action button. A substitution can have the following status:

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors, but with a message you should review.

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors.

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *ERROR* for substitutions with errors, that you can repair from the *Action* column.


Currently you can only view the details of a created substitution, but cannot edit it.

</td>
</tr>
</table>



### *Substitutes For* Tab

Choose the *Substitutes For* tab to search for substitution rules, where the user you have been searching by has the role of the substitute.


<table>
<tr>
<th valign="top">

Substitutions List

</th>
<th valign="top">

Substitution Details

</th>
</tr>
<tr>
<td valign="top">

The substitution list in the *Substitutes For* tab contains substitution rules, where the user you are searching for has the role of the substitute. The substitution is named after the substituted user.

Choose a rule from this list to see more details about it in the details area.

A substitution can have the following status:

-   *Ongoing*

-   *Ongoing \(Not Active\)*

-   *Upcoming*


The status of the substitutions is also color-coded as follows:

-   Green: No errors \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\)

-   Orange: Needs your attention. There is at least one error in this substitution \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

-   Gray: Upcoming substitution without errors, or inactive unexpected substitutions.


To activate the substitution for an unplanned absence, click the toggle button. The status of the substitution changes from *Ongoing Not Active* to *Ongoing*.

</td>
<td valign="top">

In the *Substitutes For* view you can find more information about the substitute, the scope of the substitution, and a calendar displaying the substitution period.

In the *Scope* table you can see in which task providers the substitution is created and its status for the specific task provider system. A substitution can have the following status:

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors, but with a message you should review.

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors.

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *ERROR* for substitutions with errors.


Currently you can only view the details of a created substitution, but cannot edit it.

</td>
</tr>
</table>



<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_i3t_lhz_gwb"/>

## Add a Substitution

To add a new substitution, choose *Create Substitution* and add the following information:

1.  *Substitution Type*

    Specify whether the substitution rule is for a planned absence that you know about ahead of time, or for an unexpected absence, for example, a substitute for when you're on unplanned sick leave.

2.  *Supported Task Providers* \(mandatory\)

    Choose the task providers for which the substitution rule should apply. This list contains only the active task providers that support substitutions.

3.  *Substitution Period* \(mandatory\)

    Choose a time period for the validity of the substitution rule. Planned absences can start on the same day or in the future. The time period for unexpected absences is from the time that it's created, with no end date.

    > ### Note:  
    > The substitution starts applying at 00:00 UTC on the start date and ends at 23:59 UTC on the end date.

4.  *Substitute* \(mandatory\)

    Type at least three symbols before starting the search, and choose your substitute from the suggested entries.

5.  Choose *Add* to save and enable the substitution.

    The *Add* button is enabled as soon as you’ve filled in the mandatory fields.


The substitution rules are automatically activated on the start date that you selected, and are automatically deactivated on the end date \(UTC\). On the start date of the substitution your substitute will automatically receive the tasks that you’ve defined in the substitution rule. On the end date of the substitution your substitute will automatically stop receiving the tasks that you’ve defined in the substitution rule.

> ### Tip:  
> Once you’ve created a substitution rule, make sure that you check its status in the *Scope* table of the substitution details, or in the *Substitutions* list to the left.
> 
> If there is a warning icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the status, this means that something went wrong for at least one task provider and you might need to repair the substitution from the *Repair* button in the *Actions* column in the table of the detailed view.

On the start date of the substitution, an *On Behalf Of* filter is available in the Web app of your substitute. For more information, see [Working with the Task List](working-with-the-task-list-fe4a8b3.md).



<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_oys_rhz_gwb"/>

## Delete a Substitution

To delete a substitution, select the rule from the *Substitutions* list and choose *Delete* \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\). If the deletion was successful, you get a message for the successful deletion and the rule disappears from the list of substitution rules.

> ### Note:  
> If the deletion does not succeed or succeeds only partially \(for some task providers\), the successfully removed task providers disappear from the scope list in the detailed view. The status of the remaining task providers in the list remains unchanged, and the rule might apply further until the task provider is deleted from the remaining scope list.

A substitution is automatically deleted after expiring.

**Related Information**  


[Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md "Review the list of the supported solutions and use cases in SAP Task Center.")

