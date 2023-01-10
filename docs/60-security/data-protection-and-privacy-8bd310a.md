<!-- loio8bd310af7d424384a0895062d7b8901a -->

# Data Protection and Privacy

Governments place legal requirements on industry to protect data and privacy. We provide features and functions to help you meet these requirements.

For general information about data protection and privacy on SAP Business Technology Platform \(SAP BTP\), see the SAP Business Technology Platform \(SAP BTP\) documentation under [Data Protection and Privacy](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7e513d31704a4a87831191e504ca850a.html).

SAP does not provide legal advice in any form. SAP software supports data protection compliance by providing security features and data protection-relevant functions, such as blocking and deletion of personal data. In many cases, compliance with applicable data protection and privacy laws is not covered by a product feature. Furthermore, this information should not be taken as advice or a recommendation regarding additional features that would be required in specific IT environments. Decisions related to data protection must be made on a case-by-case basis, taking into consideration the given system landscape and the applicable legal requirements. Definitions and other terms used in this documentation are not taken from a specific legal source.

> ### Caution:  
> Do not use the SAP Task Center service for storing and processing sensitive personal data.



<a name="loio8bd310af7d424384a0895062d7b8901a__section_my2_djp_h3b"/>

## Read Logging

An information report is a collection of data relating to a data subject. A data privacy specialist may be required to provide such a report or an application may offer a self service.

> ### Recommendation:  
> Task provider applications, which store sensitive personal data in their tasks data, must not be configured to supply tasks to SAP Task Center.

For audit needs, SAP Task Center offers an export feature. For more information, see [Export SAP Task Center Service Data](../40-administration/export-sap-task-center-service-data-1dfb750.md).



<a name="loio8bd310af7d424384a0895062d7b8901a__section_fpl_2qh_j3b"/>

## Audit Logging

When exporting SAP Task Center service data, the SAP Task Center writes security category logs into the audit log handled by the platform itself. For more information, see [Export SAP Task Center Service Data](../40-administration/export-sap-task-center-service-data-1dfb750.md).

For more information about accessing audit logs, see [Audit Log Retrieval API Usage for the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/30ece35bac024ca69de8b16bff79c413.html) and [Audit Log Viewer for the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e3baa5f1a0c64c44aac8ab3ea3d1b500.html).



<a name="loio8bd310af7d424384a0895062d7b8901a__section_wmc_ytp_h3b"/>

## Deletion of Personal Data

When handling personal data, consider the legislation in the different countries where your organization operates. After the data has passed the end of purpose, regulations may require you to delete the data. However, additional regulations may require you to keep the data longer. During this period, you must block access to the data by unauthorized persons until the end of the retention period, when the data is finally deleted.

Personal data can also include referenced data. The challenge for deletion and blocking is first to handle referenced data and then other data, such as business partner data.

As part of the SAP Business Technology Platform \(SAP BTP\) offboarding process, all data stored within SAP Task Center is deleted.

> ### Note:  
> Erasing the SAP Task Center destination configuration, which is used for SAP Task Center connector configuration, deletes all tasks from the `Task Cache` that have been fetched via this destination. For more information, see [Deactivate the SAP Task Center](../40-administration/deactivate-the-sap-task-center-2183b2b.md).



<a name="loio8bd310af7d424384a0895062d7b8901a__section_bmw_hvp_h3b"/>

## Change Log

SAP Task Center is not a system of record. The SAP Task Center instances do not allow changes of personal data that is temporarily stored in the `Task Cache`, so there are no change logs to maintain.

