<!-- loiob66e0cdd6e8a4ca08efd8a29b0a20b24 -->

# Using the SAP Task Center API

The SAP Task Center API for the Cloud Foundry environment allows you to list and work with user tasks and task definitions, monitor connector configurations, and export service data.

The SAP Task Center API comprises a set of REST methods that provide functionalities related to:

-   Task consumption

-   Monitoring connector status

-   Data export


For more information about the base URL, see [Get the Service Configuration Parameters](get-the-service-configuration-parameters-e10e7b2.md).



<a name="loiob66e0cdd6e8a4ca08efd8a29b0a20b24__section_xq1_tl4_qjb"/>

## Access the API Documentation

See the [SAP Business API Hub Task Center API documentation](https://api.sap.com/package/SAPTaskCenter?section=Artifacts).



<a name="loiob66e0cdd6e8a4ca08efd8a29b0a20b24__section_zyv_xl4_qjb"/>

## Authentication and Authorization

The SAP Task Center API is protected with OAuth 2.0 client credentials.

The OAuth2 authentication type \(authorization code and SAML 2.0 Bearer Assertion Flow for OAuth 2.0\) is supported. Certain authentication mechanisms are managed transparently by the application router for Cloud Foundry applications that are bound to the SAP Task Center service.

For example, the application router provides user-centric authentication mechanisms. For this purpose, it manages the current user’s authorization tokens for the back-end services in the user session. When there is no user session, the user is redirected to the UAA's logon form.

Create an OAuth client and obtain an access token to call the SAP Task Center API methods. For more information, see [Accessing Administration Using APIs of the SAP Authorization and Trust Management Service](https://help.sap.com/docs/btp/sap-business-technology-platform/accessing-administration-using-apis-of-sap-authorization-and-trust-management-service?version=Cloud).



<a name="loiob66e0cdd6e8a4ca08efd8a29b0a20b24__section_w2p_cr4_qjb"/>

## Rate Limits

To ensure optimal operation of the service, REST API execution is subject to resource limits, for example, regarding the number of requests per second. If the limits are exceeded, API calls return *HTTP status 429*: ***Too many requests. The caller has sent too many requests in a given amount of time.*** The client should then reduce the number of calls.

**Related Information**  


[Get the Service Configuration Parameters](get-the-service-configuration-parameters-e10e7b2.md "In the Cloud Foundry environment, you often require basic configuration parameters of the SAP Task Center to access the Task Center API.")

[Get the Service Host](get-the-service-host-4e38c03.md "The base URL of the SAP Task Center service is available from the endpoints.inbox_rest_url configuration parameter of the service key or of the service binding, depending on your application type.")

[Access the SAP Task Center API Using OAuth 2.0 Authentication \(Authorization Code Grant\)](access-the-sap-task-center-api-using-oauth-2-0-authentication-authorization-code-grant-29928a7.md "This procedure illustrates how to call SAP Task Center APIs using OAuth 2.0 authentication using an example walk-through of the authorization code flow. It shows how several OAuth2 concepts are specifically applied to SAP Task Center, and which configuration parameters are used.")

