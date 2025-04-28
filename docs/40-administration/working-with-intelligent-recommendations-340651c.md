<!-- loio340651ccd0724869b487f92411bda2c8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with Intelligent Recommendations

You can create intelligent recommendation model to manage recommedations for the approval tasks.



<a name="loio340651ccd0724869b487f92411bda2c8__prereq_qm1_yw2_ccc"/>

## Prerequisites

-   You've set up the SAP Task Center Administration application and you have the `TaskCenterBusinessAdministrator` role assigned. For more information, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).

-   You have the destination configured for Intelligent Recommendations. For more information, see [Configure the Intelligent Recommendations Destination](configure-the-intelligent-recommendations-destination-7c8900a.md).




<a name="loio340651ccd0724869b487f92411bda2c8__context_qll_yw2_ccc"/>

## Context

Intelligent recommendations assist users in making decision to approve or reject specific tasks. These recommendations are based on the confidence level generated for the task. Confidence level is a numeric value calculated by a trained AI model. This value assists the user in deciding the action to take on a specific task. Confidence levels and intelligent recommendations improve productivity for end users who need to approve or reject a task. Users can see the confidence level for the assigned task to make an informed decision.

To create an intelligent recommendation model, follow the procedure:



<a name="loio340651ccd0724869b487f92411bda2c8__steps_ot1_zw2_ccc"/>

## Procedure

1.  In the Task Center Administration tile, navigate to the *Intelligent Recommendations* tab.

2.  Select *Create Model* option to create a new intelligent recommendation model.

3.  In the *Create Intelligent Recommendation Model* dialog box, provide the following details:

    -   *Task Provider*: Select the required provider or connector from the dropdown list. The dropdown only displays the task providers that support intelligent recommendations.

    -   *Task Type*: Select the task for which you want to configure a recommendation.

    -   *Model Name*: Enter a name for the model.

    -   *Description*: Enter a brief description about the model.


    Configure the following *Task Type Attributes*:

    -   *Numerical Attributes*: Select the attributes from the dropdown list whose values might be subject to change. For example: NetValue, RequiredQuantity.

    -   *Categorical Attributes*: Select the attributes from the dropdown list whose values are definite and may not change. For example: Product ID, Product Name, SalesOrganization.


    > ### Note:  
    > To create a model, you must configure at least five Numerical and Categorical attribute values together.
    > 
    > Initially, the Categorical Attributes and the Numerical Attributes dropdowns display all the custom attributes. However, when a custom attribute is selected in one category, it's no longer displayed in the other category.

4.  Choose *Create*.

    An intelligent recommendation model is created and is listed under *Intelligent Recommendations* with the *Preparing Data* status. The model transitions to *In Training* status once 1000 tasks have been completed following the creation of the Intelligent Recommendation model.

5.  Once the model is *Ready for Activation*, select *Activate* option.

    The status of the model is set to *Active* and the intelligence recommendation capabilities are accessible to the users.

    > ### Tip:  
    > -   To edit a model, choose the model from the list and choose :pencil2:.
    > -   To deactivate a model, choose the required model from the list and choose *Deactivate* option.
    > -   To delete a model, choose the required model from the list and choose:wastebasket:.


**Related Information**  


[Working with the Task List](../70-using-the-web-app/working-with-the-task-list-fe4a8b3.md "In the SAP Task Center Web app, you can search for a specific task in the task list, and filter or sort your user tasks by predefined criteria. You can also refresh the task list and personalize the table columns.")

[Data Protection and Privacy](../60-security/data-protection-and-privacy-8bd310a.md "Governments place legal requirements on industry to protect data and privacy. We provide features and functions to help you meet these requirements.")

