---

title:  Retrieve Authorization Token

description:

---

# Retrieve Authorization Token {#retrieve-authorization-token}

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

Retrieves authorization (AuthZ) Token.  

  
| Endpoint | Called  </br>By | Input   </br>Params | HTTP  </br>Method | Response | HTTP  </br>Response |
| --- | --- | --- | --- | --- | --- |
| <SP_FQDN>/api/v1/tokens/authz</br></br>For example:</br></br><SP_FQDN>/api/v1/tokens/authz | Streaming App</br></br>or</br></br>Programmer Service | 1.  requestor (Mandatory)</br>2.  deviceId (Mandatory)</br>3.  resource (Mandatory)</br>4.  device_info/X-Device-Info (Mandatory)</br>5.  _deviceType_</br>6.  _deviceUser_ (Deprecated)</br>7.  _appId_ (Deprecated) | GET | 1.  Success</br>2.  Authentication Token  </br>    not found or expired:   </br>    XML explaining reason  </br>    for authn token not found</br>3.  Authorization token  </br>    not found:  </br>    XML explanation</br>4.  Authorization token  </br>    expired:  </br>    XML explanation | 200 - Success  </br>412 - No AuthN</br></br>404 - No AuthZ</br></br>410 - AuthZ Expired |

{style="table-layout:auto"}

</br>
  
| Input Parameter | Description |
| --- | --- |
| requestor | The Programmer requestorId for which this operation is valid. |
| deviceId | The device id bytes. |
| resource | A string that contains a resourceId (or MRSS fragment), identifies the content requested by a user and is recognized by MVPD authorization endpoints. |
| device_info/</br></br>X-Device-Info | Streaming Device information.</br></br>**Note**: This MAY be passed device_info as a URL paramater, but due to the potential size of this paramater and limitations on the length of a GET URL, it SHOULD be passed as X-Device-Info n the http header. </br></br>See the full details in [Passing Device and Connection Information](http://tve.helpdocsonline.com/passing-device-information). |
| _deviceType_ | The device type (e.g. Roku, PC).</br></br>If this parameter is set correctly, ESM offers metrics that are [broken down per device type](http://tve.helpdocsonline.com/esm-overview$clientless_device_type) when using Clientless, so that different types of analysis can be performed for e.g. Roku, AppleTV, Xbox etc.</br></br>http://tve.helpdocsonline.com/clientless-device-type-benefits-on-pass-metrics</br></br>**Note**: the device_info will replace this parameter. |
| _deviceUser_ | The device user identifier. |
| _appId_ | The application id/name. </br></br>**Note**: the device_info replaces this parameter. |



### Sample Response {#response}

 

#### Success

**XML:**

```XML 
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <authorization>
        <expires>1348148289000</expires>
        <mvpd>sampleMvpdId</mvpd>
        <requestor>sampleRequestorId</requestor>
        <resource>sampleResourceId</resource>
        <proxyMvpd>sampleProxyMvpdId</proxyMvpd>
    </authorization>
```

 

**JSON:**

```JSON 
    {
        "mvpd": "sampleMvpdId",
        "resource": "sampleResourceId",
        "requestor": "sampleRequestorId",
        "expires": "1348148289000",
        "proxyMvpd": "sampleProxyMvpdId"
    }
```

 </br>


#### Authentication Token not found or expired:

**XML:**

```XML 
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <error>
        <status>412</status>
        <message>User not authenticated</message>
    </error>
```

 

**JSON:**

```JSON 
    {
        "status": 412,
        "message": "User not authenticated",
        "details": null
    }
```

</br>
 

#### Authorization Token not found:

**XML:**

```XML 
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <error>
        <status>404</status>
        <message>Not found</message>
    </error>
```

 

**JSON:**

```JSON 
    {
        "status": 404,
        "message": "Not Found",
        "details": null
    }
```

</br>

 

#### Authorization Token expired:

**XML:**

```XML 
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <error>
        <status>410</status>
        <message>Gone</message>
    </error>
```

 

**JSON:**

```JSON 
    {
        "status": 410,
        "message": "Gone",
        "details": null
    }
```

 

### [Back to Clientless API Reference](http://tve.helpdocsonline.com/clientless-api-reference)
