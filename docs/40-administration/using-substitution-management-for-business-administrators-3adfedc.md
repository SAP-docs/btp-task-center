<!-- loio3adfedca4e344487ba9c5135e4fabfa7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using Substitution Management for Business Administrators

As a business administrator you can search by users and manage their existing substitution rules.



<a name="loio3adfedca4e344487ba9c5135e4fabfa7__section_tys_xgy_rcc"/>

## Prerequisites

-   You've set up the SAP Task Center Administration application and you have the `TaskCenterBusinessAdministrator` role assigned. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).

-   The task providers must have enabled the substitution management for business administrators feature. For more information, see [Supported Features](../10-what-is/supported-features-257a0ad.md).




## Concept

In the *Substitution Management* tab in the Task Center Administration app, business administrators can search for the existing substitution rules of end users, delete substitutions, or create substitutions on behalf of the end users.

> ### Note:  
> SAP Task Center works only with substitutions created in the *Substitution Management* of SAP Task Center. Substitutions created in the task providers are not supported.

![An interactive image of the substitution management for business
							administrators views. Highlights the most important actions related to
							the task.](images/SubstitutionManagement-BusinessAdmin_7c5db0d.png)



<a name="loio3adfedca4e344487ba9c5135e4fabfa7__section_CreateSubstitution"/>

## Create a Substitution Rule

To create a substitution rule on behalf of an end user, choose *Create Substitution* and add the following information:

1.  *Substituted User* \(mandatory\)

    Search for the name of the user to be substituted. You are creating the substitution rule on behalf of this user.

2.  *Choose Task Provider* \(mandatory\)

    Choose the task providers, for which the substitution rule should apply. This list contains only the active task providers, which support substitutions.

3.  *Substitution Period* \(mandatory\)

    Choose a time period for the validity of the substitution rule. It can start on the same day or in the future.

    > ### Note:  
    > The substitution starts applying at 00:00 UTC on the start date and ends at 23:59 UTC on the end date.

4.  *Substituted By* \(mandatory\)

    Type at least three symbols before starting the search, and choose your substitute from the suggested entries.

5.  Choose *Create* to save and enable the substitution.

    The *Create* button is enabled as soon as you’ve filled in the mandatory fields.


The substitution rules are automatically activated on the start date, and are automatically deactivated on the end date \(UTC\). On the start date of the substitution the substitute will automatically receive the tasks defined in the substitution rule and can access them via the *On Behalf Of* filter in their SAP Task Center Web app. On the end date of the substitution, the substitute will automatically stop receiving the tasks defined in the substitution rule.

> ### Tip:  
> Once you’ve created a substitution rule, make sure that you check its status in the *Scope* table of the substitution details, or in the substitutions list to the left.
> 
> If there is a warning icon \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\) in the status, this means that something went wrong for at least one task provider and you might need to repair the substitution from the *Repair* button in the *Actions* column in the table of the detailed view.



<a name="loio3adfedca4e344487ba9c5135e4fabfa7__section_Search"/>

## Search for Substitution Rules by User

To search for existing substitution rules, type the name of an end user in the search field in the upper right corner and choose one of the tabs above the first column:



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

-   *Upcoming*


The status of the substitutions is also color coded as follows:

-   Green: No errors \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\)

-   Orange: Needs your attention. There is at least one error in this substitution \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

-   Gray: Upcoming substitution without errors




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

-   *Upcoming*


The status of the substitutions is also color coded as follows:

-   Green: No errors \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\)

-   Orange: Needs your attention. There is at least one error in this substitution \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

-   Gray: Upcoming substitution without errors




</td>
<td valign="top">

In the *Substitutes For* view you can find more information about the substitute, the scope of the substitution, and a calendar displaying the substitution period.

In the *Scope* table you can see in which task providers the substitution is created, its status for the specific task provider system, and optionally an action button. A substitution can have the following status:

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors, but with a message you should review.

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *OK* for substitutions without errors.

-   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *ERROR* for substitutions with errors, that you can repair from the *Action* column.


Currently you can only view the details of a created substitution, but cannot edit it.

</td>
</tr>
</table>



<a name="loio3adfedca4e344487ba9c5135e4fabfa7__section_Delete_Substitution"/>

## Delete a Substitution

A substitution is automatically deleted after it expires.

To manually delete a substitution before its expiration date, proceed as follows:

1.  In the search field in the upper right corner type the name of the user, who has the role of the a substituted user or the substitute.

2.  Choose a substitution rule from the list in the first column and choose *Delete* \(<span style="color:#346187;"><span class="SAP-icons-V5"></span></span>\).

    If the deletion was successful, you get a message for the successful deletion and the rule disappears from the list of substitution rules.

    > ### Note:  
    > If the deletion does not succeed or succeeds only partially \(for some task providers\), the successfully removed task providers disappear from the scope list in the detailed view. The status of the remaining task providers in the list remains unchanged, and the rule might apply further until the task provider is deleted from the remaining scope list.


**Related Information**  


[Substitution Management](../70-using-the-web-app/substitution-management-bef9b2d.md "Use Substitution Management to access and maintain your substitutions.")

[Supported Solutions and Use Cases](../10-what-is/supported-solutions-and-use-cases-758209c.md "Review the list of the supported solutions and use cases in SAP Task Center.")

[Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md "In the SAP Task Center Web app, you can search for a specific task in the task list, and filter or sort your user tasks by predefined criteria. You can also refresh the task list and personalize the table columns.")

[Supported Features](../10-what-is/supported-features-257a0ad.md "See the SAP Task Center features, supported by SAP, or third-party task providers.")

