---
title: Ad resolvers
description: Ad resolvers
copied-description: yes
---

# Ad resolvers {#ad-resolvers}

```
if (resource.metadata != null) { 
    if (resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_DELETE_RANGES_METADATA_KEY) 
            || resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_REPLACE_RANGES_METADATA_KEY) 
            || resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_AD_MARKERS_METADATA_KEY)) 
    { 
        // Use the CustomRangesOpportunityGenerator for custom ranges opportunities 
        result.push(new CustomRangesOpportunityGenerator());  
        if (resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_DELETE_RANGES_METADATA_KEY))  { 
            result.push(new AdSignalingModeOpportunityGenerator());       
            // Manifest cue mode ignores replace range 
            result.push(new SpliceOutOpportunityGenerator()); 
        } 
        return result; 
    } 
}
```