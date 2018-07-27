---
description: Alternate, or late-binding, audio allows you to switch among available audio tracks for a video track. This way, users can select a language track when the video is played.
seo-description: Alternate, or late-binding, audio allows you to switch among available audio tracks for a video track. This way, users can select a language track when the video is played.
seo-title: Alternate audio
title: Alternate audio
uuid: 99a75c94-a110-49fb-abca-776eb84f87d0
index: n
internal: n
snippet: y
translate: y
---

# Alternate audio

<!-- All of these code samples are C++. They were all C++ in the original topic file too, that is, for all platforms. Wrong. Wrong. Wrong. --> 
<a id="section_E4F9DC28A2944BD08B4190A7F98A8365"></a>

When  <!-- PH element: phrases/primetime-sdk-name --> creates the ` MediaPlayerItem` instance for the current video, it creates an ` AudioTrack` item for each available audio track. The item contains a ` name` property, a string that typically contains a user-recognizable description of the language of that track. The item also contains information about whether to use that track by default. 
When it is time to play the video, you can ask for a list of available audio tracks, optionally let the user choose one, and set the video to play with the selected track.
Although rare, if an additional audio track becomes available after it creates the ` MediaPlayerItem`,  <!-- PH element: phrases/primetime-sdk-name --> fires a ` MediaPlayerItem.AUDIO_UPDATED` event. 

## Added APIs {#section_87C42C30BA8C4F58A2DAB7CE07FCD3DE}

The following APIs have been added to support alternate audio:
` hasAlternateAudio` 
If the specified media has an alternate audio track, other than default track, this boolean function returns ` true`. If there is no alternate audio track, the function returns ` false`. 
```
bool MediaPlayerItemImpl::hasAlternateAudio() const { 
    return _hasAlternateAudio; 
}
```

** ` getAudioTracks`** 
This function returns list of all the current available audio tracks in a specified media. 
```
virtual PSDKErrorCode getAudioTracks(PSDKImmutableArray&lt;AudioTrack&gt;*&amp; out) const { 
if (_audioTracks) { 
    out = _audioTracks; 
    out-&gt;addRef(); 
    return kECSuccess; 
    } 
    return kECDataNotAvailable; 
} 

```

` getSelectedAudioTrack` 
This function that returns the currently selected alternate audio track and properties such as language. The auto-selection of track can also be extracted. 
```
PSDKErrorCode MediaPlayerItemImpl::getSelectedAudioTrack(AudioTrack &amp;out) const { 
    out = _currentAudioTrack; 
    return kECSuccess; 
}
```

` selectAudioTrack` 
This function selects an alternate audio track to play. 
```
PSDKErrorCode MediaPlayerItemImpl::selectAudioTrack(const AudioTrack &amp;audioTrack) { 
    _lastPlayedAudioTrack = _currentAudioTrack; 
    if(_mediaPlayer &amp;&amp; _mediaPlayer-&gt;_trickPlay) 
        return kECUnsupportedOperation; 
    _currentAudioTrack = audioTrack; 
    PSDKErrorCode result = kECSuccess; 
    if (_currentAudioTrack) { 
        media::TimeLine* timeline = NULL; 
        if (_mediaPlayer-&gt;_fragHttpStreamer) 
            _mediaPlayer-&gt;_fragHttpStreamer-&gt;GetTimeLine(&amp;timeline); 
        if (timeline) { 
            for (int32_t i = timeline-&gt;GetFirstPeriodIndex(); i &lt;= timeline-&gt;GetLastPeriodIndex(); i++){ 
                media::ErrorCode error = selectTrack(timeline,_mediaPlayer-&gt;_fragHttpStreamer, i, audioTrack.getName(), media::kSTTAudioIndex); 
                return _mediaPlayer-&gt;convertToPSDKError(error); 
            } 
        } 
    }   
    return result; 
}
```
