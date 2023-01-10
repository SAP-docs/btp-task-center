<!-- loioa0be9ad5cd7146fca3ac29b92ab631dc -->

# Configure Labels in SAP Task Center Web App

You can configure labels to be displayed below the task titles in your SAP Task Center Web app.

When setting up a destination, you can configure the *tc.ui.label* parameter and add *tc.ui.label.\[language\_code\]* parameters for other languages, to visualize additional information about the task.

If you want to use translations for the task labels, you have to add the default *tc.ui.label* property and then also add the property for the respective language *tc.ui.label.\[language\_code\]*, for example *tc.ui.label.de-DE* for German translations. For more information about the supported languages, see [Supported Languages](../10-what-is/supported-languages-c66c693.md).

Depending on your user language, the SAP Task Center searches for available translations as follows:

-   If there is a *tc.ui.label.\[language\_code\]* property defined for the user language, then the task label translations for this language are visualized in the respective language.

-   If the *tc.ui.label.\[language\_code\]* property for the user language is not defined, but the default *tc.ui.label* property is defined, then the task label translations are visualized in the default language.

-   If there are no *tc.ui.label* and *tc.ui.label.\[language\_code\]* properties defined, no labels are visualized.


**Related Information**  


[Destinations](destinations-3470733.md "The SAP Task Center communicates with the task provider applications via predefined destinations in a customer subaccount.")

