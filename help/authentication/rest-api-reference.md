---
title: REST API Reference
description: Rest api reference
exl-id: 5fea0310-371d-405a-b661-f8f5874d802b
---
# REST API Reference {#rest-api-reference}

>[!NOTE]
>
>The content on this page is provided for information purposes only. Usage of this API requires a current license from Adobe. No unauthorized use is permitted.

## Response Formats {#response-formats}


>[!NOTE] 
>
> The APIs provided in these services can return responses in either XML or JSON (for APIs that return a response). There are 3 different ways to specify the response format in the request: 
>* Set HTTP Accept Header to "<code>application/xml</code>" or "<code>application/json</code>"
>* In the request payload, specify the parameter "<code>format=xml</code>" or "<code>format=json</code>"</li>
>* Call the web service endpoint with extension <code>.xml</code> or <code>.json</code>. For example, "<code>/regcode.xml</code>" or "<code>/regcode.json</code>"
>
>You can specify any ONE of the above methods. Specifying multiple methods with conflicting formats may result in errors or undesirable output.

## REST API Endpoints {#clientless-endpoints}

<REGGIE_FQDN>:

* Production - [api.auth.adobe.com](http://api.auth.adobe.com/)
* Staging - [api.auth-staging.adobe.com](http://api.auth-staging.adobe.com/)

<SP_FQDN>:

* Production - [api.auth.adobe.com](http://api.auth.adobe.com/)
* Staging - [api.auth-staging.adobe.com](http://api.auth-staging.adobe.com/)

</br>


## Web Services Summary {#web_srvs_summary}

The table below lists the available web services for the clientless approach. Click the web services endpoints for more information (sample request and response, input parameters, HTTP methods, etc.)

  
| Sr  | Web Service Endpoint | Description | [Diag.  </br>Ref](http://tve.helpdocsonline.com/api-reference-v2-test#illustration). | Hosted At | Called By |
| --- | --- | --- | --- | --- | --- |
| 1.  | [<REGGIE_FQDN>/reggie/v1/  </br>  {requestorId}/regcode](http://tve.helpdocsonline.com/registration-code-request) | Returns randomly generated registration Code and login Page URI | 2   | Adobe  </br>Reg Code Service | Smart Device |
| 2.  | [<REGGIE_FQDN>/reggie/v1/  </br>  {requestorId}/regcode/  </br>  {registrationCode}](http://tve.helpdocsonline.com/return-registration-record) | Returns registration code record containing registration code UUID, registration code, and hashed device ID | 8   | Adobe  </br>Reg Code Service | Primetime authentication |
| 3.  | [<SP_FQDN>/api/v1/config/  </br>  {requestorId}](http://tve.helpdocsonline.com/provide-mvpd-list) | Returns list of configured MVPDs for the requestor | 5   | Adobe  </br>Primetime  </br>authentication  </br>Service | Login  </br>Web  </br>App |
| 4.  | [<SP_FQDN>/api/v1/authenticate](http://tve.helpdocsonline.com/initiate-authentication) | Initiates the AuthN process by informing MVPD selection event. Creates a record on authentication database, which is reconciled when a successful response is received from MVPD (Step 13) | 7   | Adobe  </br>Primetime  </br>authentication  </br>Service | Login  </br>Web  </br>App |
| 5.  | SAML Assertion Consumer | Existing SAML workflow between Primetime authentication and MVPD | 13  | Primetime  </br>authentication  </br>Service | Primetime authentication |
| 6.  | [<SP_FQDN>/api/v1/checkauthn/  </br>  {registrationCode}](http://tve.helpdocsonline.com/check-authentication-flow-by-second-screen-web-app) | The Login Web App can check if the attempted login flow was successful |     | Primetime  </br>authentication   </br>Service | Login   </br>Web   </br>App |
| 7.  | [<SP_FQDN>/api/v1/tokens/authn](http://tve.helpdocsonline.com/rest-api-retrieve-authentication-token) | Gets AuthN token related metadata | 15  | Primetime  </br>authentication  </br>Service | Smart Device |
| 8.  | [<REGGIE_FQDN>/reggie/v1/  </br>  {requestorId}/regcode/  </br>  {registrationCode}](http://tve.helpdocsonline.com/delete-registration-record) | Deletes the reg code record and releases the reg code for reuse | 16  | Adobe  </br>Reg Code Service | Primetime authentication |
| 9.  | [<SP_FQDN>/api/v1/authorize](http://tve.helpdocsonline.com/initiate-authorization) | Obtains authorization response. | 17  | Primetime  </br>authentication  </br>Service | Smart Device |
| 10. | [<SP_FQDN>/api/v1/checkauthn](http://tve.helpdocsonline.com/check-authentication-token) | Indicates whether the device has an unexpired AuthN token. |     | Primetime  </br>authentication  </br>Service | Smart Device |
| 11. | [<SP_FQDN>/api/v1/tokens/authn](http://tve.helpdocsonline.com/rest-api-retrieve-authentication-token) | Returns the AuthN token if found. |     | Primetime  </br>authentication  </br>Service | Smart Device |
| 12. | [<SP_FQDN>/api/v1/tokens/authz](http://tve.helpdocsonline.com/retrieve-authorization-token) | Returns the AuthZ token if found. |     | Primetime  </br>authentication  </br>Service | Smart Device |
| 13. | [<SP_FQDN>/api/v1/tokens/media](http://tve.helpdocsonline.com/obtain-short-media-token) | Returns the Short Media Token if found - same as /api/v1/mediatoken |     | Primetime  </br>authentication  </br>Service | Smart Device |
| 14. | [<SP_FQDN>/api/v1/mediatoken](http://tve.helpdocsonline.com/obtain-short-media-token) | Obtains Short Media Token |     | Primetime  </br>authentication  </br>Service | Smart Device |
| 15. | [<SP_FQDN>/api/v1/preauthorize](http://tve.helpdocsonline.com/retrieve-list-of-preauthorized-resources) | Retrieves the list of preauthorized resource |     | Primetime  </br>authentication  </br>Service | Smart Device |
| 16. | [<SP_FQDN>/api/v1/preauthorize/{code}](http://tve.helpdocsonline.com/retrieve-list-of-preauthorized-resources-by-way-of-web-app) | Retrieves the list of preauthorized resources |     | Primetime  </br>authentication  </br>Service | Login Web App |
| 17. | [<SP_FQDN>/api/v1/logout](http://tve.helpdocsonline.com/logout) | Remove AuthN and AuthZ tokens from storage |     | Primetime  </br>authentication   </br>Service | Smart Device |
| 18. | [<SP_FQDN>/api/v1/tokens/usermetadata](http://tve.helpdocsonline.com/user-metadata-call) | Gets user metadata after authentication flow completes | N/A | N/A | Smart Device |
| 19. | [<SP_FQDN>/api/v1/authenticate/freepreview](http://tve.helpdocsonline.com/free-preview-for-temp-pass-and-promotional-temp-pass) | Create an authentication token for Temp Pass or Promotional Temp Pass | N/A | Primetime  </br>authentication  </br>Service | Smart Device |

{style="table-layout:auto"}

## REST API Security {#security}

All Primetime authentication clientless APIs must be called using the HTTPS protocol for secure communication. In addition, most of the APIs called should contain an access token provided by [Dynamic Client Registration](http://tve.helpdocsonline.com/dynamic-client-registration).


## Related Information {#related}

* [REST API Overview](http://tve.helpdocsonline.com/reset-api-overview)
* [Server-to-Server Cookbook](http://tve.helpdocsonline.com/server-to-server-cookbook)
* [Client-to-Server Cookbook](http://tve.helpdocsonline.com/client-to-server)
* [Avoid using '&'reg\_code in /authenticate request (Tech Note)](https://tve.zendesk.com/entries/23648011-Clientless-Avoid-using-reg-code-in-authenticate-request)
