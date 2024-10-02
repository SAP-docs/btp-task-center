<!-- loiobef9b2d6ec6a4c6f858e936fcdf9a4c5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Substitution Management

Use *Substitution Management* to access and maintain your substitutions.

When planning your absence you can add substitution rules in the SAP Task Center Web app, so that, for the period that you define, your substitute can work on your tasks, displayed directly in their Web app.

Open the **<span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Substitution Management* view from the user menu in the upper right corner of your SAP Task Center Web app.

For more information on the task providers, supporting *Substitution Management*, see [Supported Features](../10-what-is/supported-features-257a0ad.md).

> ### Note:  
> -   SAP Task Center works only with substitutions created in the *Substitution Management* of SAP Task Center. Substitutions created in the task providers are not supported.
> 
> -   Business administrators can use the substitution management feature in the Task Center Administration app and create or manage substitution rules of behalf of end users. For more information, see [Using Substitution Management for Business Administrators](../40-administration/using-substitution-management-for-business-administrators-3adfedc.md).



<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_hts_1wb_svb"/>

## Prerequisites

-   To access the *Substitution Management* option in the SAP Task Center Web app, there must be at least one active task provider, which supports substitutions. Otherwise the *Substitution Management* option is not available in the user menu.

-   To create a substitution for a specific task provider, this task provider must support substitutions.




<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_g5r_fyb_svb"/>

## Substitution Management View

The *Substitution Management* view consists of the following areas:

-   *Substitutions*

    Contains substitutions, added by you. Choose a rule from this list to see more details about it in the details area.

    A substitution can have the following status:

    -   *Ongoing*

    -   *Upcoming*


    The status of the substitutions is also color coded as follows:

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



<a name="loiobef9b2d6ec6a4c6f858e936fcdf9a4c5__section_i3t_lhz_gwb"/>

## Add a Substitution

To add a new substitution, choose *Add Substitution* and add the following information:

1.  *Supported Task Providers* \(mandatory\)

    Choose the task providers, for which the substitution rule should apply. This list contains only the active task providers, which support substitutions.

2.  *Substitution Period* \(mandatory\)

    Choose a time period for the validity of the substitution rule. It can start on the same day or in the future.

    > ### Note:  
    > The substitution starts applying at 00:00 UTC on the start date and ends at 23:59 UTC on the end date.

3.  *Substitute* \(mandatory\)

    Type at least three symbols before starting the search, and choose your substitute from the suggested entries.

4.  Choose *Add* to save and enable the substitution.

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

