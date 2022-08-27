---
title: Initiate Authentication
description: Initiate authentication
exl-id: b10b0ebd-33be-417c-af31-08b476394c5e
---
# Initiate Authentication {#initiate-authentication}

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

Initiates the authentication process by informing of an MVPD selection
event. Creates a record on the Primetime authentication database, which
is reconciled when a successful response is received from the MVPD. 


  
| Endpoint | Called  </br>By | Input   </br>Params | HTTP  </br>Method | Response | HTTP  </br>Response |
| --- | --- | --- | --- | --- | --- |
| <SP_FQDN>/api/v1/authenticate | AuthN Module | 1.  requestor_id (Mandatory)</br>2.  mso_id (Mandatory)</br>3.  reg_code (Mandatory)</br>4.  domain_name (Mandatory)</br>5.  noflash=true -  </br>    (Mandatory, Residual parameter)</br>6.  no_iframe=true (Mandatory, Residual parameter)</br>7.  extra parameters (Optional)</br>8.  redirect_url (Mandatory) | GET | The Login Web App is redirected to the MVPD login page. | 302 for full redirect implementations |

{style="table-layout:auto"}


| Input Parameter | Description |
| --- | --- |
| requestor_id   | The Programmer requestor for which this operation is valid. |
| mso_id | The MVPD ID for which this operation is valid.|
| reg_code | The registration code generated by the Reggie service. |
| domain_name | The originating domain. |
| redirect_url | The Login Webapp redirect url after authentication completion. |

{style="table-layout:auto"}

</br>

>[!IMPORTANT] 
> 
>**Important: Mandatory parameters -** Regardless of the client-side implementation, all the parameters above are mandatory. 
>
>
>Example:     
>
>```
>domain_name=loginwebapp.com
>mso_id=sampleMvpdId
>reg_code=RO0885W
>requestor_id=sampleRequestorId
>noflash=true
>redirect_url=http://loginwebapp.com
>```

>[!IMPORTANT] 
> 
>**Important: Optional parameters**
>
>The call may also contain optional parameters that enable other functionalities like:
>
> * generic\_data - enables the use of [Promotional TempPass](https://tve.helpdocsonline.com/promotional-temp-pass)
>
>```JSON
>Example:
>  generic_data=("email":"email@domain.com")
>```


### **Notes** {#notes}

* The value of the `domain_name` parameter must be set to one of the domain names registered with Primetime authentication. For more details, refer to [Registration and Initialization](http://tve.helpdocsonline.com/new-programmer-overview$reg_and_init).

* [Avoid using '&'reg\_code in /authenticate request (Tech Note)](https://tve.helpdocsonline.com/clientless:-avoid-using-'&'reg_code-in-/authenticate-request)

* The `redirect_url` parameter must be the last one in order

* The value of the `redirect_url` parameter must be URL-Encoded

[Back to REST API Reference](http://tve.helpdocsonline.com/rest-api-reference)