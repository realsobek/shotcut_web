---
layout: page
title: Configuration Keys
category: notes
---

<!-- Shotcut Responsive -->
<ins class="adsbygoogle"
    style="display:block"
    data-ad-client="ca-pub-1305424236533187"
    data-ad-slot="3403753557"
    data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>

### Location

If an `appdatadir` folder is supplied (see below), the configuration file is
named shotcut.ini in the folder. Otherwise, where the configuration lives
depends on the operating system:

**Windows**

The settings are
stored in the registry at key
HKEY\_CURRENT\_USER\\Software\\Meltytech\\Shotcut\\.

**Linux**

The settings are stored in \~/.config/Meltytech/Shotcut.conf, which is a
text file in INI format.

**macOS**

The settings are stored in
\~/Library/Preferences/com.Meltytech.Shotcut.plist, which is a [binary
plist](https://developer.apple.com/library/mac/documentation/Darwin/Reference/Manpages/man5/plist.5.html)
file.

### Keys

How the category appears depends on the config file format. Linux conf and Windows INI file uses sections (square brackets), Windows registry uses a sub-key (except General), and macOS plist
prefixes the key name followed by a period and the key (except General). In 
Windows registry, a bool is stored as a string: true or false.

| Key              | Type        | Description
|------------------|-------------|------------
| ***General***
| language         | string      | lowercase, two-letter ISO 639 language code, or &lt;language&gt;_&lt;country&gt; where &lt;country&gt; is an uppercase, two- or three-letter ISO 3166 country code (Settings > Language)
| imageDuration    | real number | the default duration of a newly opened image file
| openPath         | string      | the file system path for the file-open dialog
| savePath         | string      | the file system path for the file-save dialog
| recent           | string list | list of recent media and XML files with full path: comma-separated in Linux or Windows INI, multi-string in Windows registry, and array of strings in macOS plist (View > Recent)
| theme            | string      | UI theme, one of: dark, light, or system (Settings > Theme)
| titleBars        | bool        | whether to show the title bar for UI panels (View > Show Title Bars)
| toolBar          | bool        | whether to show the main tool bar at the top of the main window (View > Show Toolbar)
| geometry         | binary      | the size and position of the windows
| geometryDefault  | binary      | used to save View > Layout > Restore Default Layout
| windowState      | binary      | the current layout of the UI panels
| windowStateDefault | binary    | used to save View > Layout > Restore Default Layout
| showConvertClipDialog | bool   | whether to continue to show the Convert to Edit-friendly dialog for variable frame rate or non-seekable files
| drawMethod       | integer     | Settings > Display Method (Windows only), one of: 0 (Automatic), 15 (OpenGL), or 16 (DirectX)
| noupgrade        | bool        | whether to show the prompt to check for upgrade upon app launch
| appdatadir       | string      | the file system path where to load configuration. If this is set, then all the remaining configuration keys are read from shotcut.ini instead of the registry (Windows), plist (macOS), or ~/.config (Linux).
| ***playlist***
| viewMode         | string      | one of: detailed, icons, or tiled
| thumbnails       | string      | how to show the thumbnails in the Playlist panel, one of: hidden, wide, tall, small, large
| ***encode***
| path             | string      | the file system path for Export > Export File
| freeSpaceCheck   | bool        | whether to continue checking if a storage volume has sufficient space for storing Video
| ***player***
| audioChannels    | integer     | the number of audio channels to use (Settings > Audio Channels)
| deinterlacer     | string      | one of: onefield, linearblend, yadif-nospatial, or yadif (Settings > Deinterlacer)
| external         | string      | for Settings > External Monitor, one of: sdi (Linsys card), decklink:&lt;N&gt; (Blackmagic Design peripheral), or &lt;N&gt; (screen)
| gamma            | string      | for Settings > Gamma (GPU Effects only), one of: iec61966_2_1 (sRGB) or bt709 (Rec. 709)
| gpu              | bool        | whether Settings > GPU Effects is on
| jack             | bool        | whether Settings > Use JACK Audio is on
| interpolation    | string      | for Settings > Interpolation, one of: nearest, bilinear, bicubic, or hyper (Lanczos)
| keyer            | integer     | for Settings > External Monitor > Decklink Keyer, one of: 0 (Off), 1 (Internal), 2 (External)
| muted            | bool        | whether the player volume is muted
| profile          | string      | for Settings > View Mode, see file names in share/mlt/profiles for a list of values or blank for Automatic
| progressive      | bool        | whether Settings > Progressive is on
| realtime         | bool        | whether Settings > Realtime is on
| scrubAudio       | bool        | whether Settings > Scrub Audio is on
| volume           | integer     | the player volume level as a percentage
| zoom             | real number | the player's current zoom level as a factor from 0 to 2 where 0 means "Fit"
| ***timeline***
| thumbnails       | bool        | Timeline > menu > Show Video Thumbnails
| waveforms        | bool        | Timeline > menu > Show Audio Waveforms
| rippleAllTracks  | bool        | Timeline > menu > Ripple All Tracks
| snap             | bool        | Timeline > Toggle snapping
| ripple           | bool        | Timeline > Ripple trim and drop
| ***filter***
| favorite/&lt;filterId&gt; | string | whether a filter is chosen as favorite, one of: yes or no. See all the meta.qml files in share/shotcut/qml/filters for the filter IDs.
| audioInDuration  | real number | the default Fade Audio In duration in seconds
| audioOutDuration | real number | the default Fade Audio Out duration in seconds
| videoInDuration  | real number | the default Fade Video In duration in seconds
| videoOutDuration | real number | the default Fade Video Out duration in seconds
| ***scope***
| loudness/integrated | bool     | View > Scopes > Audio Loudness > menu > Integrated Loudness
| loudness/shortterm | bool     | View > Scopes > Audio Loudness > menu > Short Term Loudness
| loudness/momentary | bool     | View > Scopes > Audio Loudness > menu > Momentary Loudness
| loudness/range | bool     | View > Scopes > Audio Loudness > menu > Loudness Range
| loudness/peak | bool     | View > Scopes > Audio Loudness > menu > Peak
| loudness/truepeak | bool     | View > Scopes > Audio Loudness > menu > True Peak
| ***layout***
| layouts          | string list| the names of all of the custom saved layouts
| &lt;custom layout name&gt;_geometry | binary | the size and position of the windows
| &lt;custom layout name&gt;_state | binary | the layout of the UI panels
{:.withborders}


<!-- Shotcut Responsive -->
<ins class="adsbygoogle"
    style="display:block"
    data-ad-client="ca-pub-1305424236533187"
    data-ad-slot="3403753557"
    data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
