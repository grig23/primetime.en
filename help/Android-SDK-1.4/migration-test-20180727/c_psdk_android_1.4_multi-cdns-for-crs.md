---
description: While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.
seo-description: While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.
seo-title: Multiple CDN support for CRS ad delivery
title: Multiple CDN support for CRS ad delivery
uuid: 8db8302d-3bcf-48c2-ac98-90b7f73bffaf
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
* ` URLTransformer` An interface that describes the methods that are required to transform the CRS ad URLs that are requested by  <!-- PH element: phrases/primetime-sdk-name --> . Applications can implement and provide implementations for the required methods. 

* ` DefaultURLTransformer` The default URL transformer instance that is created in  <!-- PH element: phrases/primetime-sdk-name --> and that implements the ` URLTransformer`  Applications can override this class or add a post URL transformation handler. This handler is useful when the application wants to make changes to the URL request after the default transformation has been applied. 

* ` NetworkConfiguration.setURLTransformer` A setter method that is provided on the ` NetworkConfiguration` metadata instance to set the ` URLTransformer` implementation. 



>[!IMPORTANT]
>
>Your app implementations must check for the ` URLTransformerInputType` enumeration and only transform URLs of type ` URLTransformerInputType.CRSCreative` for CRS. 

The following code sample shows how your application can change the default host component to a different string (for example, ` cdn.mycrsdomain.com`): 
```
javaNetworkConfiguration networkConfiguration = new NetworkConfiguration(); 
DefaultURLTransformer urlTransformer = new DefaultURLTransformer(); 
urlTransformer.addPostURLTransformHandler(new DefaultURLTransformer.URLTransformHandler() { 
    @Override 
    public String call(String url, URLTransformerInputType type) { 
        if (type == URLTransformerInputType.CRSCreative) { 
            try { 
                return url.replaceAll(new java.net.URI(url).getHost(), "cdn.mycrsdomain.com"); 
            } catch (URISyntaxException e) { 
            } 
        } 
        return url; 
    } 
}); 
   
networkConfiguration.setURLTransformer(urlTransformer); 
   
// metadata is the Metadata instance set on a MediaResource instance. 
metadata.setNode(DefaultMetadataKeys.NETWORK_CONFIGURATION.getValue(), networkConfiguration);
```
