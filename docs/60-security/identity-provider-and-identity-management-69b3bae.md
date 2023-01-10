<!-- loio69b3baed13ca4a9f933c69a48f54755c -->

# Identity Provider and Identity Management

For identity management and authentication, the SAP Task Center tenant relies on the Identity Authentication as the identity provider \(IdP\) that is configured in the customer subaccount that owns the respective subscriptions.

All requests handled by the SAP Task Center subscriptions are authenticated against the Identity Authentication, which is configured in the customer subaccount and authorized against the role assignments, specified on the subscriptions in the customer subaccount.

All task provider tenants must have trust between the Identity Authentication tenant that was configured during the initial setup of SAP Task Center. See the prerequisites in [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md) or [Manual Setup](../30-initial-setup/manual-setup-0f00d3d.md).

For more information about setting up task provider tenants, and Identity Authentication and Identity Provisioning, see [System Integration Guide for SAP Cloud Identity Services](https://help.sap.com/viewer/b95c3d5bab324a3a8409eee5267a5b75/Cloud/en-US).

**Related Information**  


[Map Role Collections to User Groups](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/51acfc82c0c54db59de0a528f343902c.html)

[Manually Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7c6aa87459764b179aeccadccd4f91f3.html)

[System Integration Guide for SAP Cloud Identity Services](https://help.sap.com/viewer/b95c3d5bab324a3a8409eee5267a5b75/Cloud/en-US)

