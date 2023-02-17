<!-- loio29928a76d13e4d81a88e5774e9ca194e -->

# Access the SAP Task Center API Using OAuth 2.0 Authentication \(Authorization Code Grant\)

This procedure illustrates how to call SAP Task Center APIs using OAuth 2.0 authentication using an example walk-through of the authorization code flow. It shows how several OAuth2 concepts are specifically applied to SAP Task Center, and which configuration parameters are used.



<a name="loio29928a76d13e4d81a88e5774e9ca194e__section_kc4_vkg_dlb"/>

## Prerequisites

-   You have executed the [Initial Setup](../30-initial-setup/initial-setup-8347694.md) and as result you have an existing service instance of the SAP Task Center instance, created either by the booster execution, or manually.
-   Assign the necessary role collections of the SAP Task Center API that you want to call to the user on whose behalf the call to the SAP Task Center API is executed. Typically, this is the user who authenticates the call to the OAuth 2.0 authorization endpoint. If you have executed the [Automatic Setup](../30-initial-setup/automatic-setup-3a49967.md), your user already has the necessary permissions.

    For more information about role collections, see [Assign Roles to Your Users](../60-security/assign-roles-to-your-users-7e081d8.md).

    For more information about roles, see [Authorization Configuration](../60-security/authorization-configuration-75e4130.md).




<a name="loio29928a76d13e4d81a88e5774e9ca194e__section_rbz_tlg_dlb"/>

## Context

SAP Task Center supports Authorization Code Grant flow for accessing its APIs.

> ### Note:  
> You must apply URL encoding to all the parameters that contain special characters, for example, the `uaa.clientid` and `redirect_uri` parameters.



<a name="loio29928a76d13e4d81a88e5774e9ca194e__section_b2q_2mg_dlb"/>

## Procedure

1.  Get the following service configuration parameters as described in [Get the Service Configuration Parameters](get-the-service-configuration-parameters-e10e7b2.md):
    -   `uaa.clientid`
    -   `uaa.clientsecret`
    -   `uaa.url`
    -   `endpoints.inbox_rest_url`

2.  Request an authorization code from the OAuth 2.0 authorization server.
    1.  Send a ***GET*** request to the authorization endpoint and specify both the client ID and the response type as *code*. Use the `uaa.url` and `uaa.clientid` service configuration parameters.

        > ### Example:  
        > Combine the parameters with the `uaa.url` endpoint of the authorization server, as follows: *****<uaa.url\>********/oauth/authorize?client\_id=********<URL encoded uaa.clientid\>********&response\_type=code&redirect\_uri=http://localhost*** and open this URL in a browser.

    2.  Authenticate the call using the real user that should be propagated to the SAP Task Center API \(on behalf of the user\).

        > ### Example:  
        > If you would like to call the connector status API, the user that you authenticate with, must have the ***TaskCenterAdmin*** role assignment. For more information, see: [Assign Roles to Your Users](../60-security/assign-roles-to-your-users-7e081d8.md).

        The response redirects to the URL similar to: ***http://localhost:8080/?code=<authorization\_code\>***.

        > ### Note:  
        > If the error *This site can't be reached* appears, get the redirect URL from the address bar of the browser.

        The value of the parameter code represents the authorization code.

    3.  Copy the `authorization_code` from the *HTTP URL*.

3.  Request an access token from the OAuth 2.0 authorization server.

    1.  Send a POST request to the token endpoint and specify the grant type as the authorization code. Use the `uaa.url` service configuration parameter and the `authorization_code` from the previous step.

        > ### Example:  
        > Combine the parameters with the `token` endpoint of the authorization server. For example: *****<uaa.url\>********/oauth/token?grant\_type=authorization\_code&code=<authorization\_code\>&redirect\_uri=http://localhost***

    2.  Authenticate the call using basic authentication, where the username corresponds to your OAuth client ID and the password - to the client secret. Use the respective service configuration parameters `uaa.clientid` \(not URL encoded\) and `uaa.clientsecret`.

        > ### Example:  
        > ***curl -X POST "<url\>/oauth/token?redirect\_uri=http://localhost" -H "Content-Type: application/x-www-form-urlencoded" -u "<uaa.clientid\>:<uaa.clientsecret\>" -d "grant\_type=authorization\_code&code=<authorization\_code\>"***

    3.  Copy the access token from the HTTP response body \(`access_token` attribute of the JSON structure\).

    > ### Note:  
    > If the access token expires before you get to execute the last step, use a refresh token.

    The HTTP response in the step *Request an access token from the OAuth 2.0 authorization server*includes a refresh token \(`refresh_token` attribute\). It is typically used when the lifetime of the returned access token has expired but the application still wants to execute an HTTP request \(as in the next step\) on behalf of the given user. You can use the refresh token to request a new access token for the user without again asking the user for consent. The new access token then replaces the old one with a new lifetime.

    To request a new access token for a given refresh token, send a POST request to the same token endpoint as in the step *Request an access token from the OAuth 2.0 authorization server* passing the refresh token. The call must be authenticated again with basic authentication, where the username corresponds to your OAuth client ID and the password to the client secret.

    > ### Example:  
    > Combine the parameters with the `token` endpoint of the authorization server. For example: *****<uaa.url\>********/oauth/token?grant\_type=refresh\_token&refresh\_token=<refresh\_token\>***.

    However, it is important to understand that the refresh token has a lifetime as well. Lifetimes of access and refresh tokens can be configured separately. If the lifetime of the refresh token has expired, there is no means to request a new refresh token.

4.  Perform the call to the SAP Task Center API by sending the access token as the header. Use the endpoints below the base URL from the service configuration parameter `endpoints.inbox_rest_url`.
    1.  Header name: ***Authorization***
    2.  Header value: ***Bearer <access token\>***

        > ### Example:  
        > Access Connector status API:
        > 
        > ***curl "<endpoints.inbox\_rest\_url\>/v1/connectorStatus" -H "Authorization: Bearer <access token\>"***



**Related Information**  


[Access the SAP Task Center API using Postman](https://blogs.sap.com/2021/06/08/access-the-sap-task-center-api-using-postman/)

