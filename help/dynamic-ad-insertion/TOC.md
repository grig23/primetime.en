---
cloud: experience-cloud
product: adobe primetime
audience: end-user
user-guide-title: Primetime Dynamic Ad Insertion Help
user-guide-description: Explains how to monetize content by inserting user-targeted dynamic ads on the server and engage audience with personalized ads.
---

# Dynamic Ad Insertion Help {#ad-insertion}

+ [Dynamic Ad Insertion Overview](home.md)
+ Get started with Primetime Ad Insertion{#get-started}
  + [Overview](get-started-ptai.md)
  + [Prepare to use Primetime Ad Insertion](setup-ptai.md)
  + [Integrate your ad server](integrate-ad-server.md)
  + [Integrate your CDN](integrate-cdn.md)
  + [Use ad insertion in live/linear streams](ad-insertion-live-linear-stream.md)
  + [Use ad insertion for VOD](ad-insertion-vod.md)
  + [Set up ad tracking](set-up-ad-tracking.md)
+ [Dynamic Ad Insertion Release Notes](https://docs.adobe.com/content/help/en/primetime/release-notes/ptai/ptai-19x-release-notes.html)
+ [Manifest Server Debugging Tool](manifest-server-debugging-tool.md)
<!-- + [Server Side Ad Insertion debugging dashboard](ssai-debugging-dashboard.md)-->
+ Manifest Server API for Ad Insertion {#manifest-server}
  + [Overview of Manifest Server interactions](msapi-topics/ms-overview.md)
  + Get started with Manifest Server {#get-started}
    + [Send a command to the Manifest Server](msapi-topics/ms-getting-started/ms-sending-cmd.md)
    + [Manifest server query parameters](msapi-topics/ms-getting-started/ms-api-query-params.md)
  + Ad insertion requests {#ad-insert}
    + [Requests for ad insertion](msapi-topics/ms-insert-ads/ms-ad-insert.md)
    + [Optional query parameters by client and situation](msapi-topics/ms-insert-ads/ms-api-query-param-situation.md)
    + [Facilitating HLS player switching to failover/backup streams](msapi-topics/ms-insert-ads/hls-switching-to-failover.md)
    + [Multiple bit rate streams](msapi-topics/ms-insert-ads/ms-api-mbr-streams.md)
    + [Partial Ad Break Insertion](msapi-topics/ms-insert-ads/partial-ad-break-insetion.md)
    + [Multiple CDN support for CRS ad delivery](msapi-topics/ms-insert-ads/ms-api-multi-cdns-for-crs.md)
  + Replace VOD timelines {#replace-vod}
    + [Changes to VOD](msapi-topics/ms-changes-vod-timeline/ms-replace-vod-timeline.md)
    + [VOD timeline format](msapi-topics/ms-changes-vod-timeline/ms-api-timeline-format.md)
    + [Replace a VOD timeline](msapi-topics/ms-changes-vod-timeline/t-ms-replace-vod-timeline.md)
  + Ad effectiveness tracking {#ad}
    + [Ad tracking](msapi-topics/ms-at-effectiveness/ms-at-overview.md)
    + [Enable client-side ad tracking](msapi-topics/ms-at-effectiveness/ms-enable-client-side-ad-tracking.md)
    + [Overview of non-TVSDK client-side tracking](msapi-topics/ms-at-effectiveness/notvsdk-csat-overview.md)
    + [API for players to interact with the manifest server](msapi-topics/ms-at-effectiveness/notvsdk-csat-ms-interface.md)
    + [EXT-X-MARKER Directive](msapi-topics/ms-at-effectiveness/ms-api-playlists.md)
  + [Cookies](msapi-topics/ms-cookies.md)
  + [Support for WebVTT captions](msapi-topics/ms-webvtt-captions.md)
  + List of file formats {#list}
    + [File formats](msapi-topics/ms-list-file-formats/ms-api-file-formats.md)
    + [JSON format for URL for requesting variant manifest playlist](msapi-topics/ms-list-file-formats/ms-json-m3u8.md)
    + [JSON formats for tracking URLs](msapi-topics/ms-list-file-formats/notvsdk-csat-sidecar.md)
    + [VMAP format for tracking URLs](msapi-topics/ms-list-file-formats/notvsdk-csat-vmap.md)
  + [Video player requirements](msapi-topics/ms-player-req.md)
+ Primetime Creative Repackaging Service {#crs}
  + [Overview of CRS](creative-repackaging-service/crs-overview.md)
  + [Main Uses of CRS](creative-repackaging-service/jit-async-hls-conv.md)
  + [Multi CDN support](creative-repackaging-service/multi-cdn-supportt.md)
  + [Detailed Workflows for JIT Repackaging](creative-repackaging-service/jit-repackage.md)
  + [Using CRS to Inject ID3 Timed Metadata Tags](creative-repackaging-service/inject-id3.md)
  + [Repackaging API](creative-repackaging-service/api-repackage.md)
