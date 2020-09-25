---
title: Bootstrap API
description: 
---

# Bootstrap API {#bootstrap-api}

Required Parameters
Generate a bootstrap

## Parameter description {#parameter-description}

| parameter | description | formats |
|---|---|---|
| pabimode | Enables [partial ad break insertion](ad-insertion-live-linear-stream.md#partial-ad-break-support) for Live streams. Possible values:true to enableomit to disable (default disabled) | HLS/DASH |
| ptadwindow | Duration (in seconds) of the lookback ad decisioning window -- how far back Primetime Ad Insertion will look for ad cues when a DVR user joins the stream. A value of zero will disable mid-roll ad decisioning in the initial manifest, with decisioning resuming only after the first update. This parameter is useful to disable ad insertion into sessions that may only last a few seconds (aka channel flipping). Possible values:numeric string 0-1800 (default 1800) | HLS only |
| ptassetid | Unique ID of the content that is assigned and maintained by publisher.  Required when used in conjunction with the Akamai Ad Scaler. | HLS/DASH |
| ptcdn | List of one or more CDNs to host transcoded assets. For more information, see [Multi CDN support](multi-cdn-support.md). Possible values: akamai, level3, llnw (limelight networks), comcastBy default, Primetime Ad Insertion CDNs are used | HLS/DASH |
| ptcueformat | The specified format of tags to perform ad decisioning (for example, scte35). Possible values: dpisimple, dpiscte35, elemental For custom cue formats, please contact your technical account representative for the value to use for your use case | HLS/DASH |  
| ptfailover | Signals the manifest server to identify primary and failover streams specified in the master playlist, and to treat them as disjoint sets. This facilitates failover and prevents timing errors. (For Apple HLS devices only.) For more information, see [Facilitating HLS player switching](hls-switching-to-failover.md) | HLS only |
| ptmulticall | If enabled, a separate ad request is made for each avail found in a VOD asset.  By default, Primetime Ad Insertion will attempt to collect all avail information and send it to the ad server in one request. Possible values:true to enableomit to disable (default disabled) | HLS/DASH |
| pttagds | Enables injection of EXT-X-DISCONTINUITY-SEQUENCE tags into HLS headers.Possible values:true to enableomit to disable (default disabled) | HLS only |
| pttimeline | A string containing the desired timeline for ad placement and content, which overrides ad breaks in the content stream. [ See VOD Timeline Format ] | HLS/DASH |
| pttoken | Enables content fragment/segment authorization token protection schemes for CDNs Possible values: akamai, llnw (limelight), ctl (centurylink) (default tokenization is disabled) | HLS/DASH |
| pttrackingmode | Enable ad tracking schemes:Possible values:simple for client-side ad trackingsstm for server-side ad tracking simplesstm for hybrid client/server ad tracking (by default, no ad tracking is performed) | HLS/DASH |
| pttrackingversion |||
| ptadtimeout (as in 20.9.2)|||
| ptparallelstream (as in 20.9.3)|||
