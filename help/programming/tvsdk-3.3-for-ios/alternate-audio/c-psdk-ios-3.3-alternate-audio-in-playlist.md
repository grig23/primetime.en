---
description: Alternate, or late-binding, audio allows you to switch among available audio tracks for a video track. This way, users can select a language track when the video is played.
seo-description: Alternate, or late-binding, audio allows you to switch among available audio tracks for a video track. This way, users can select a language track when the video is played.
seo-title: Alternate audio tracks in the playlist
title: Alternate audio tracks in the playlist
uuid: 6241d3e4-6e07-44fb-bc0e-5d49d1a76824
index: y
internal: n
snippet: y
---

# Alternate audio tracks in the playlist {#alternate-audio-tracks-in-the-playlist}

Alternate, or late-binding, audio allows you to switch among available audio tracks for a video track. This way, users can select a language track when the video is played.

When TVSDK creates the `MediaPlayerItem` instance for the current video, it creates an `AudioTrack` item for each available audio track. The item contains a `name` property, a string that typically contains a user-recognizable description of the language of that track. The item also contains information about whether to use that track by default.

When it is time to play the video, you can ask for a list of available audio tracks, optionally let the user choose one, and set the video to play with the selected track.

Although rare, if an additional audio track becomes available after it creates the `MediaPlayerItem`, TVSDK fires a `MediaPlayerItem.AUDIO_UPDATED` event.

## Added APIs {#section_87C42C30BA8C4F58A2DAB7CE07FCD3DE}

The following APIs have been added to support alternate audio:

`hasAlternateAudio`

If the specified media has an alternate audio track, other than default track, this boolean function returns `true`. If there is no alternate audio track, the function returns `false`. 

```
bool MediaPlayerItemImpl::hasAlternateAudio() const 
{ 
    return _hasAlternateAudio; 
}
```

** `getAudioTracks`**

This function returns list of all the current available audio tracks in a specified media. 

```
virtual PSDKErrorCode getAudioTracks(PSDKImmutableArray<AudioTrack>*& out) const 
    { 
        if (_audioTracks) 
        { 
            out = _audioTracks; 
            out->addRef(); 
            return kECSuccess; 
        } 
        return kECDataNotAvailable; 
    }
```

`getSelectedAudioTrack`

This function that returns the currently selected alternate audio track and properties such as language. The auto-selection of track can also be extracted. 

```
PSDKErrorCode MediaPlayerItemImpl::getSelectedAudioTrack(AudioTrack &out) const 
{ 
    out = _currentAudioTrack; 
    return kECSuccess; 
}
```

`selectAudioTrack`

This function selects an alternate audio track to play. 

```
PSDKErrorCode MediaPlayerItemImpl::selectAudioTrack(const AudioTrack &audioTrack) 
{ 
    _lastPlayedAudioTrack = _currentAudioTrack; 
    if(_mediaPlayer && _mediaPlayer->_trickPlay) 
        return kECUnsupportedOperation; 
    _currentAudioTrack = audioTrack; 
    PSDKErrorCode result = kECSuccess; 
    if (_currentAudioTrack) 
    { 
        media::TimeLine* timeline = NULL; 
        if (_mediaPlayer->_fragHttpStreamer) 
            _mediaPlayer->_fragHttpStreamer->GetTimeLine(&timeline); 
        if (timeline) 
        { 
            for (int32_t i = timeline->GetFirstPeriodIndex(); i <= timeline->GetLastPeriodIndex(); i++){ 
                media::ErrorCode error = selectTrack(timeline,_mediaPlayer->_fragHttpStreamer, i, audioTrack.getName(), media::kSTTAudioIndex); 
                return _mediaPlayer->convertToPSDKError(error); 
            } 
        } 
    }   
    return result; 
}
```

## Alternate audio tracks in the playlist {#section_BC8C1C74A5A24A8CA68C1E7E721EE742}

The playlist for a video can specify an unlimited number of alternative audio tracks for the main video content. For example, you might want to add different languages to your video content or allow the user to switch between different tracks on their device while the content is playing.

Alternate audio tracks, or late-binding audio, allows users to switch between multiple language tracks for HTTP video streams (live/linear and VOD), and you do not have to modify, duplicate, or repackage the video for each audio track. You can provide multiple language tracks for a video asset before or after the asset’s initial packaging.

>[!TIP]
>
>For the alternate audio to be mixed with the video track of the main media, the timestamps of the alternate track must match the timestamps of the audio in the main track.

The following requirements apply if you use alternate audio tracks and incorporate advertising:

* If the main content has alternate audio tracks, ads must have at least one audio-only stream. 
* Each segment duration of an ad's audio-only stream must be equal to the segment duration of an ad's video stream.

The main audio track is included in the audio tracks collection with the `default` label. Metadata for the alternate audio streams is included in the playlist in the `#EXT-X-MEDIA` tags with `TYPE=AUDIO`.

For example, an M3U8 manifest that specifies multiple alternate audio streams might look like this: 

```
#EXTM3U 
#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="bipbop_audio",LANGUAGE="eng",NAME="BipBop Audio 1", 
 AUTOSELECT=YES,DEFAULT=YES 
#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="bipbop_audio",LANGUAGE="eng",NAME="BipBop Audio 2", 
 AUTOSELECT=NO,DEFAULT=NO,URI="alternate_audio_aac/prog_index.m3u8" 
#EXT-X-MEDIA:TYPE=SUBTITLES,GROUP-ID="subs",NAME="English",AUTOSELECT=YES,FORCED=NO, 
 LANGUAGE="eng",URI="subtitles/eng/prog_index.m3u8" 
#EXT-X-MEDIA:TYPE=SUBTITLES,GROUP-ID="subs",NAME="English (Forced)",DEFAULT=YES, 
 AUTOSELECT=YES,FORCED=YES,LANGUAGE="eng",URI="subtitles/eng_forced/prog_index.m3u8" 
#EXT-X-MEDIA:TYPE=SUBTITLES,GROUP-ID="subs",NAME="Français",AUTOSELECT=YES,FORCED=NO, 
 LANGUAGE="fra",URI="subtitles/fra/prog_index.m3u8" 
#EXT-X-STREAM-INF:PROGRAM-ID=1,BANDWIDTH=263851,CODECS="mp4a.40.2, avc1.4d400d", 
 RESOLUTION=416x234,AUDIO="bipbop_audio",SUBTITLES="subs"  
gear1/prog_index.m3u8 
#EXT-X-STREAM-INF:PROGRAM-ID=1,BANDWIDTH=577610,CODECS="mp4a.40.2, avc1.4d401e", 
 RESOLUTION=640x360,AUDIO="bipbop_audio",SUBTITLES="subs" 
gear2/prog_index.m3u8 
... 

```
