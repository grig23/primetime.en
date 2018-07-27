---
description: While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.
seo-description: While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.
seo-title: Multiple CDN support for CRS ad delivery
title: Multiple CDN support for CRS ad delivery
uuid: 4bad2775-1ad7-47b8-b60c-2727babb8731
index: n
internal: n
snippet: y
translate: y
---

# Multiple CDN support for CRS ad delivery

You can use multiple CDNs for the following reasons: 
* A requirement to scale up for large viewing events.
* A requirement to match the CDN source of the CRS asset with the CDN source of the main content.

You can transform the default URL that is provided by the CRS by using  <!-- PH element: phrases/primetime-sdk-name --> URL Transformer APIs.
Here are the API additions in  <!-- PH element: phrases/primetime-sdk-name --> :
* ` PTURLTransformer` A protocol that describes the methods that are required to transform the CRS ad URLs that are requested by  <!-- PH element: phrases/primetime-sdk-name --> . Applications can implement this protocol and provide implementations for the required methods.

* ` PTDefaultURLTransformer` The default URL transformer instance that is created in  <!-- PH element: phrases/primetime-sdk-name --> and that implements the ` PTURLTransformer` protocol. Applications can override this class or add a post URL transformation handler. This handler is useful when the application wants to make changes to the URL request after the default transformation has been applied. 

* ` PTNetworkConfiguration setURLTransformer:defaultTransformer` A setter method that is provided on the ` PTNetworkConfiguration` metadata instance to set the ` PTURLTransformer` implementation. 



>[!IMPORTANT]
>
>Your app implementations must check for the ` PTURLTransformerInputType` enumeration and only transform URLs of type ` PTURLTransformerInputTypeCRSCreative` for CRS. 

The following code sample shows how your application can change the default host component to a different string (for example, ` cdn.mycrsdomain.com`): 
```
// The sample code below uses Non-ARC code 
PTNetworkConfiguration *networkConfiguration = [[[PTNetworkConfiguration alloc] init] autorelease]; 
   
PTDefaultURLTransformer *defaultTransformer = [[[PTDefaultURLTransformer alloc] init] autorelease]; 
    [defaultTransformer addPostURLTransformHandler:^NSString *(NSString *url, PTURLTransformerInputType type) { 
        if (type == PTURLTransformerInputTypeCRSCreative) { 
            return [url stringByReplacingOccurrencesOfString:[NSURL URLWithString:url].host  
              withString:@"cdn.mycrsdomain.com"]; 
        } 
            return url; 
    }]; 
  
[networkConfiguration setURLTransformer:defaultTransformer]; 
   
// metadata is the PTMetadata instance set on a PTMediaPlayerItem instance. 
[metadata setMetadata:[self getNetworkConfiguration] forKey:PTNetworkConfigurationMetadataKey];
```
