---
seo-title: JSON object for Primetime ads
title: JSON object for Primetime ads
uuid: 9c8c534d-8227-42f6-885b-d25fde795354
index: n
internal: n
snippet: y
translate: y
---

# JSON object for Primetime ads


>The code block below defines the details JSON object when the type value is Primetime ads.
>
>```
>>“metadata”: {
>    “ad” :  {
>        “type”: “Primetime ads”,
>        “details”: {
>            "domain": "sandbox2.auditude.com",
>            "mediaid": "rom_asset_case_1",
>            "zoneid": "109754",
>            "targeting": [
>                {
>                    "key": "osmfKeyMulAdsAvail12346",
>                    "value": "MulAdsAvail12346"
>                }
>            ]
>        }
>    }
>}
>
>```



>| Property |Description |
>|---|---|
>| domain |The Primetime ads domain to use for ad requests. |
>| mediaid |The mediaid that has been set up in Primetime ads for this content. |
>| zoneid |The Primetime ads zoneid. See the Primetime ads documentation for more information. |
>| targeting |An array of key/value pairs used for targeting specific ads for the content. |

>See [com.adobe.mediacore.metadata.AuditudeSettings](http://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/metadata/AuditudeSettings.html) for more information on the value of these attributes. 