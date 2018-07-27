---
description: The Primetime reference implementation uses a JSON-based feed format for responses. This format is parsed using an implementation of the IFeedItemAdapter interface.
seo-description: The Primetime reference implementation uses a JSON-based feed format for responses. This format is parsed using an implementation of the IFeedItemAdapter interface.
seo-title: Catalog format
title: Catalog format
uuid: 696c3b83-fb0f-447a-a5fb-384cb155cbdc
index: n
internal: n
snippet: y
translate: y
---

# Catalog format


>[!NOTE]
>
>This feed format is the sample format that the reference implementation uses and serves as an example of how the format can be parsed and mapped to the feed interface. You can use your own input feed format with your own feed interface implementations.


At a high-level, the format consists of an array of content entries. Each entry represents a live or VOD published video content:

```
{
    "entries": [
        {
        },
        {
        },
        ...
    ]
}

```

Each feed entry is a JSON object with a given set of attributes:

```
{
    "entries": [
        
            "id": "episode1",
            "title": "My episode1",
            "description": "This is an episode.",
            "categories": "documentary, educational, children",
            "keywords": "List, of, comma, separated, keywords",
            "isLive": false,
            "content":  [
                
                },
                
                },
            ],
            "thumbnails": [
                
                },
                
                }
            ]
            "metadata": 
            } 
        }
    ]
}

```


| Property |Description |
|---|---|
| `id`  |A unique identifier/guide for the content as set by the feed publishing system. |
| `title`  |A title for the content. |
| `description`  |A description of the content. |
| `categories`  |A list of categories tagged for the content that can be used by the application to enhance the user's experience. Read into the properties for the content. |
| `keywords`  |A list of comma separated keywords, can be used by the application to enhance the user's experience. Read into the properties for the content. |
| `isLive`  |true or false, indicating if it is a Live or VOD stream. |
| `content`  |An array of JSON objects with alternate formats for the content along with the corresponding URLs. For example, there could be urls for the f4m and m3u8 formats. The JSON object attributes are described further below. |
| `thumbnails`  |An array of JSON objects with urls for different sizes of thumbnails. The JSON object attributes are defined below. |
| `metadata`  |A JSON object defining metadata for the content, currently this metadata is limited to ad related metadata. The metadata object is defined below. |

The following code block defines the JSON objects that form the array of **content objects**: 

```
"content":  [
    {
        "format": "M3U8",
        "url": "http://adobeprimetime-f.akamaihd.net/i/
<i>longstringofcharacters</i>/
                 Episode_,640x360_1000,640x360_700,_b.mp4.csmil/master.m3u8",
        "language": "en"
    }  
],
```



<table id="table_FBCAE95B1A4A4904A7B92B26A84735D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry">Property</th> 
   <th colname="col2" class="entry">Description</th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="codeph">format</span> </td> 
   <td colname="col2"> <p>Needs to be m3u8 format for Android.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph">url</span> </td> 
   <td colname="col2">The url to the video stream for the given format.</td> 
  </tr> 
 </tbody> 
</table>

The following code block defines the JSON objects that form the array of **thumbnail objects**: 

```
"thumbnails": [
    {
        "format": "JPEG",
        "height":  "90",
        "width": "160",
        "url": "http://example.com/small.jpg"
    },
    {
        "format": "JPEG",
        "height": "450",
        "width": "800",
        "url": "http://example.com/large.jpg"
    }
],

```



| Property |Description |
|---|---|
| format |A string indicating the format of the thumbnail file, for example, JPEG, PNG, etc. |
| height |The height of the thumbnail. In the reference application, the thumbnail with smallest height and width is returned as the small thumbnail and the one with the largest width and height is returned as the large thumbnail. |
| width |The width of the thumbnail. In the reference application, the thumbnail with smallest height and width is returned as the small thumbnail and the one with the largest width and height is returned as the large thumbnail. |
| url |The url to the thumbnail file. |

The following code block defines the **metadata object**: 

```
"metadata" : {
    "ad" : {
        "type" : "",
        "details" : {
        }
    }
    "entitlement" : {
        "id" : ""
    }
}
```



<table id="table_291AE420FF684160B2E6A6F91805FB28"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry">Property</th> 
   <th colname="col2" class="entry">Description</th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1">ad</td> 
   <td colname="col2">Ad-related metadata.</td> 
  </tr> 
  <tr> 
   <td colname="col1">type</td> 
   <td colname="col2"> <p>Value can be Primetime Ads, Direct Ad Breaks, or Custom Ad Markers.</p> <p>The PSDK provides built-in support for the following types of metadata: Auditude-related metadata for Primetime Ad Serving (Primetime Ads), direct ad-breaks with ad urls (Direct Ad Breaks), and custom ad markers that provide the TimeRange for each ad marker (Custom Ad Markers). Each type has a built-in <span class="codeph">AdProvider</span> in the PSDK that processes the metadata. </p> <p>The JSON format for each of these have been define below.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">details</td> 
   <td colname="col2">Includes the ad metadata attributes. Both types of ad metadata have their own set of attributes defined below. For the built-in types, the attributes included define the data expected by the PSDK for that type.</td> 
  </tr> 
  <tr> 
   <td colname="col1">entitlement</td> 
   <td colname="col2">Entitlement related metadata</td> 
  </tr> 
  <tr> 
   <td colname="col1">id</td> 
   <td colname="col2">Media resource ID used for authorization requests against the Adobe Primetime pay-TV pass service. The ID may be either a text string or a HTML-encoded mRSS string. Any media content which requires authorization must contain a valid resource ID.</td> 
  </tr> 
 </tbody> 
</table>
