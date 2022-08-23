---

title:  Retrieve List of Preauthorized Resources by Second Screen Web App

description: A request to Adobe Primetime authentication to obtain the list of preauthorized resources.

---

# Retrieve List of Preauthorized Resources by Second Screen Web App {#retrieve-list-of-preauthorized-resources-by-second-screen-web-app}

>[!NOTE]
>
>The content on this page is provided for information purposes only. Usage of this API requires a current license from Adobe. No unauthorized use is permitted.

## REST API Endpoints {#clientless-endpoints}

<REGGIE_FQDN>:

* Production - [api.auth.adobe.com](http://api.auth.adobe.com/)
* Staging - [api.auth-staging.adobe.com](http://api.auth-staging.adobe.com/)

<SP_FQDN>:

* Production - [api.auth.adobe.com](http://api.auth.adobe.com/)
* Staging - [api.auth-staging.adobe.com](http://api.auth-staging.adobe.com/)

</br>

## Description {#description}

A request to Adobe Primetime authentication to obtain the list of preauthorized resources.

There are two sets of APIs: one set for the Streaming App or Programmer Service and one set for the Second Screen Web App. This page describes the API for the AuthN App.

   
| Endpoint | Called  </br>By | Input   </br>Params | HTTP  </br>Method | Response | HTTP  </br>Response |
| --- | --- | --- | --- | --- | --- |
| <SP_FQDN>/api/v1/preauthorize/{registration code} | AuthN Module | 1.  registration code  </br>    (Path component)</br>2.  requestor (Mandatory)</br>3.  resource list (Mandatory) | GET | XML or JSON containing individual pre-authorization decisions or error details. See samples below. | 200 - Success</br></br>400 - Bad request</br></br>401 - Unauthorized</br></br>405 - Method not allowed  </br></br>412 - Precondition failed</br></br>500 - Internal Server Error |



| Input Parameter   | Description                                                                                                                                                                    |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| registration code | The registration code value supplied by the user at the beginning of the authentication flow.                                                                                  |
| requestor         | The Programmer requestorId for which this operation is valid.                                                                                                                  |
| resource list     | A string that contains a comma delimited list of resourceIds that identifies the content that might be accessible to a user and is recognized by MVPD authorization endpoints. |


### Sample Response {#sample-response}

**XML:**

```XML
HTTP/1.1 200 OK
Adobe-Request-Id : 7af28ec2-a068-45c2-8009-f5443049baf4`
Adobe-Response-Confidence : full
Content-Type: application/xml; charset=utf-8

<resources>
    <resource>
        <id>TestStream1</id>
        <authorized>true</authorized>
    </resource>
    <resource>
        <id>TestStream2</id>
        <authorized>false</authorized>  
        <error>
            <status>403</status>
            <code>authorization_denied_by_mvpd</code>
            <message>User not authorized</message>
            <details>Your subscription package does not include the "TestStream3" channel.</details>
            <helpUrl>https://tve.helpdocsonline.com/errors/preauthorization_denied</helpUrl>
            <trace>0453f8c8-167a-4429-8784-cd32cfeaee58</trace>
            <action>none</action>
        </error>
    <resource>
</resources>
```

**JSON:**

```JSON
HTTP/1.1 200 OK
Adobe-Request-Id : 7af28ec2-a068-45c2-8009-f5443049baf4
Adobe-Response-Confidence : full
Content-Type: application/json; charset=utf-8
 
{
   "resources" : [
        {
            "id" : "TestStream1",
            "authorized" : true
        },
        {
            "id" : "TestStream3",
            "authorized" : false,
            "error" : {
               "status" : 403,
               "code" : "authorization_denied_by_mvpd",
               "message" : "User not authorized",
               "details" : "Your subscription package does not include the "TestStream3" channel.",
               "helpUrl" : "https://tve.helpdocsonline.com/errors/preauthorization_denied",
               "trace" : "0453f8c8-167a-4429-8784-cd32cfeaee58",
               "action" : "none"
            }
        } 
    ]
}
```
 

### [Back to REST API Reference](http://tve.helpdocsonline.com/rest-api-reference)
