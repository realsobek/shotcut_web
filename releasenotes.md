---
layout: page
title: Release Notes
permalink: /download/releasenotes/
category: other
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

These are brief notes about known problems and feature additions. See
[News]({{ "/blog" | prepend:site.baseurl }}) or the [git
log](https://github.com/mltframework/shotcut/commits/master) for more
information.

##### Release 18.09.16

Fixed broken color selection in the following (non-GPU) video filters:

- Chroma Key: Simple
- Chroma Key: Advanced
- Key Spill: Advanced
- White Balance

##### Release 18.09.15

- Fixed image transform regression in **Rotate and Scale**, **Size and
Position**, and **Text** filters.
- Fixed image scaling interpolation method when not using a transform filter.
- Fixed a crash applying an image transform filter to an image with alpha
channel (PNG, SVG).
- Added a highlight for the buttons in the **Filters** chooser.
- Fixed new **Ripple** and **Snapping** keyboard shortcuts not always working.
- Fixed moving a clip to another track and back not working correctly.
- Fixed dragging clips to the **Timeline** stops working.
- Fixed redo trimming the in point of clip on **Timeline** not working correctly.

##### Release 18.09.13

- Added **Ripple** support for **moving** clips including **Ripple All Tracks**.
- When **Ripple** is on and you move a clip to the right, it now
ripples (pushes) all the clips to the right instead of making a transition
(including the **Ripple All Tracks** option).
- Added **Ctrl+R** keyboard shortcut to toggle **Timeline Ripple**,  
**Ctrl+Alt+R** to toggle **Ripple All Tracks**, and  
**Ctrl+Shift+R** to toggle both.
- Improved **Snapping** behavior on the **Timeline**.
- Added **Ctrl+P** keyboard shortcut to toggle **Snapping**.
- Added **Reset Track Height** (**Ctrl+0**) to the **Timeline** menu.
- Added a **Timer** video filter.
- Added support for negative rotation to the **Rotate and Scale** filter.
- Added **Shake 1 Second - Scaled** and **Shake 1 Second - Unscaled** presets
to the Size and Position filter.
- Added a **Text** clip to the **Open Other** dialog.  
This is a convenience item that creates a transparent **Color** clip with a
**Text** filter.
- Added **Extract Sub-clip** to **Properties** menu for audio/video clip.
- Added **Export** presets for WebM VP8 and VP9 with alpha channel.
- Fixed a crash when quickly changing clip selections in the **Timeline**.
- Improved closing Shotcut more reliably and the behavior of multiple shotcut
processes.
- Fixed **Undo** beyond **Remove Track** may crash.
- Fixed a crash when moving a clip after undoing a transition.
- Fixed a crash loading project after some sequence of inserting and removing tracks.
- Fixed a crash loading an image with the wrong filename extension.
- Fixed OS audio device changes may cause Shotcut to hang.
- Fixed crash dragging simple keyframes beyond the edges of the clip.
- The 32-bit Windows build can use more memory to reduce risk of crash:  
3 GiB on 32-bit Windows and 4 GiB on 64-bit Windows.
- Improved behavior of opening WebP images.
- Fixed advanced keyframes for the **Size and Position** filter.
- Fixed inserted and then hidden video tracks become audio tracks after
re-opening the project.
- Fixed changing **Video Mode** from **Automatic** to something else with
nothing opened.
- Fixed moving a transition to another track leaves a hidden clip on the old track.
- Fixed trimming the out point of a timeline clip may change the in point of
the following clip.
- Fixed **Properties** > **Speed**, **Convert**, **Reverse**, and
**More Information** does not work sometimes after reloading a project.
- Fixed reliability of changing size and position fields with keyframes
in **Size and Position** and **Text** filters.
- Fixed trimming outward with **Ripple All Tracks** moved clips on other tracks
in the wrong direction.
- Fixed audio waveforms still appear on muted tracks after adding a track.
- Fixed edges of text with the **Text** filter may get cut off (clipped).
- Fixed **Size and Position** and **Rotate and Scale** filters may leave black
right and bottom edge of frame.
- Fixed trimming a timeline clip with **Fade In/Out Video** filters
with "Adjust opacity instead of fade with black" enabled.
- Fixed **Export** may change the actual frame rate and cause timing errors.
- Fixed reducing the **Frame/sec** in **Export** causes timing errors in the output.
- Removed the **Compositing** toggle icon from the **Timeline** track head. Now,
it is located in the track **Properties** as **Blend mode** with a **None** option.
- In the **3D Text** filter, replaced the Droid fonts with Liberation due to an
incompatible license.
- Improved the performance of changing filter parameters and scrubbing.
- Limit the number of background thumbnail and waveform generation threads to 4.
- Prevent trying to generate audio levels for waveforms for still images and
other silent sources.

##### Release 18.08.14

* Fixed regression in 18.08.11 that can put corrupt character in the .mlt XML
  project file.
* Fixed the size of an existing Text filter with animation breaks if you
  select the clip and the filter.

##### Release 18.08.11

* Fixed new crash in v18.08 changing **Settings > Video Mode** with nothing opened.
* Fixed crash while adjusting position or size in **Text** and **Size and Position** filters.
* Fixed position and size information incorrect if resolution or aspect ratio changed in **Export**.
* Fixed **Text** animation (keyframes) when not the first clip in the timeline.
* Fixed track name not editable after the track head had been selected at least once.
* Fixed right-clicking a timeline clip breaks automatic timeline scrolling during playback.
* Added Quicktime Animation **Export** preset to export video with alpha channel.
* In **Export**, let option values in **Other** tab override values generated by other fields.

##### Release 18.08.01

* Added the timecode of failure to the **Jobs** panel when an export job fails
  (makes locating problem areas in the project easier).
* Added an **Unpremultiply Alpha** video filter (handy to fix compositing for
  video clips with an alpha channel that has had its color pre-multiplied with
  its alpha).
* Fixed various crash regressions since v18.05.
* Fixed audio distortion during preview (regression in v18.07).
* Fixed custom **Export** presets broken if name contains parentheses
  (regression in v18.07).
* Fixed **Properties > Reverse...** broken if numeric region setting uses comma
  for decimal (regression in v18.07).
* Fixed **Overlay HTML** editor easily destroys default scripts (introduced in
  v18.07) if **WebVfx JavaScript extension** enabled.
* Fixed custom interlaced **Export** presets loading as progressive (regression
  in v18.07)
* Fixed **Timeline > Copy Timeline to Source > Export** fails on unsaved
  (Untitled) project.
* Fixed **Text** filter has aliased edges (regression in v18.07).
* Fixed **Stabilize** video filter not available on Linux (regression since v18.06).
* Fixed changing **Speed** in **Properties** breaks all filters on that clip
  (regression since v18.05).
* Fixed **Fade Out Video** (and keyframes in general) broken on still images
  whose in point is > 0 (regression since v18.03).
* Fixed accuracy of **Properties > Duration** for image clip on the timeline.
* Some fixes for changing **Settings > Video Mode** after starting a project.
* Fixed compositing of upper video tracks becomes broken if bottom video track
  is deleted.
* Fixed images with alpha channel (e.g. PNG) on upper video tracks have dark
  edges after compositing if the **Size and Position** or **Rotate and Scale**
  filters are not used.

##### Release 18.07

* Numerous fixes as usual.
* Changed shortcut for **Add Video Track** to `Ctrl+I`.
* Changed shortcut for **Redo** to `Ctrl+Y` on Windows.
* Added **10%** to the player zoom menu.
* Hide the VUI (video user interface) when the play head is not over the clip with the current filter.
* Renamed the Rotate filter to **Rotate and Scale**.
* Keyframes are now saved in the project file using time clock values instead of frame numbers to make them adaptive to frame rate.
* Reverted memory manager change from v18.05 pending further testing to improve stability.
* Added advanced keyframes to the **Size and Position** filter.
* Added simple and advanced keyframes to the following video filters:
  - **Rotate and Scale**
  - **Text**
  - **Glow***
  - **Contrast***
  - **Sharpen***
  - **Vignette***  
  \* = including the (still experimental) GPU filter
* Added **Copy Timeline to Source** to Timeline menu.
* Changed the audio codec to AC-3 for the edit-friendly and reverse MP4 file format.
* Changed `J` and `K` key behavior to change speed up or down before changing direction.
* Added categories to the **Export** presets (custom presets can start their name with "category)" to use a category).
* Added **View > Layout** menu for custom and stock layouts:
  - Timeline Project
  - Playlist Project
  - Clip-only Project
  - Player
* Changed the default, first-time user UI layout to **Timeline Project**.
* Changed **Properties > menu > Reverse...** to work on a trimmed clip from either **Source** or **Timeline**.
* Added **Properties** menu items to the context menus for **Timeline** and timeline clips.
* Added logic to sort GoPro files when multiple files are opened or dropped.
* Added support for setting project file name (using **File > Save**) for empty project.
* Added new HTML template for WebVfx JavaScript extensions enabled in **Overlay HTML** video filter.
* Added search field to the filter chooser in **Filters**.
* Upgraded MLT to v6.10.0

##### Release 18.06

* Many bug fixes due to introduction of keyframes and change to memory management in v18.05.
* Added simple and advanced **Keyframes** to the **Blur**, **Mask**, and **Saturation** filters.
* Added seek buttons for simple **Keyframes**.
* Added ability to add and remove advanced **Keyframes** using double-click.
* Added ability to drag advanced **Keyframes** to adjust both value and position.  
  (When dragging, hold down Ctrl key to adjust only value or Alt key to adjust only position.)
* Added double-click to toggle simple **Keyframes** controls (circles).
* Added double-click to toggle fade in/out controls (circles) on **Timeline** clip.
* Added many animated (keyframes) presets to the **Size and Position** filter.
* Added **Hue/Lightness/Saturation** video filter.
* Added **Reverse** to clip **Properties** menu.
* Added **Detach Audio** to timeline clip's context menu.
* Added 5.1 surround support to the **Copy Channel** and **Swap Channels** audio filters.
* Added caution message to GPU Effects confirmation dialog.
* Added a **Keyboard Shortcuts** link to the **Help** menu.
* Changed presets file format to YAML.
* Changed **Settings > GPU Processing** to **GPU Effects**.
* Reduced memory usage on 32-bit builds (by constraining multi-threading).
* Upgraded [FFmpeg to v4.0](http://ffmpeg.org/index.html#news).
* Integrated [AMD AMF](https://gpuopen.com/gaming-product/advanced-media-framework/) hardware-accelerated H.264 and HEVC encoders on Windows (Set **Export > Codec** to **h264_amf** or **hevc_amf**. Requires recent Radeon or AMD APU.)
* Upgraded MLT to git master ([v6.8.0](https://www.mltframework.org/blog/v6.8.0_released/) minimum required to build).

##### Release 18.05

* Added **Keyframes** for Filters:
  - Gain / Volume
  - Brightness
  - Circular Frame
  - Color Grading (no simple)
  - Opacity
  - Size and Position (simple only)
* Added support for mono and 5.1 surround sound: **Settings > Audio Channels** and **Export >Audio > Channels**.
* Added **Finnish** translation.
* Restored **GIF Animation** for Export.
* Reduced memory footprint (especially for Rotate and Size and Position filters).
* Changed **Export** default settings to reduce output size by increasing GOP and number of B frames.

##### Release 18.03

* Added a **Sketch** filter.
* Added numeric fields to the **Color Grading** filter.
* Added **All** option to **Properties > Audio > Track**.
* Added **Estonian** translation.
* Improved image loading speed on Windows.
* Improved mouse-wheel & trackpad scrolling in **Timeline**.
* Improved support for JACK Audio (Linux and macOS only).
* Upgraded FFmpeg to version 3.4 and latest vpx for much faster VP9 encoding.
* Upgrade MLT to v6.6.0.
* Upgraded SDL to version 2.0.

##### Release 18.01

* Added **Audio Spectrum Visualization** filter.
* Added support for font size and italics to **Text** filter.
* Added a **Mask** filter.
* Another important fix for accuracy of XML time values for non-integer frame rates.

##### Release 17.12

* Added icon, progress bar, and time remaining/taken to **Jobs** panel.
* Increased maximum resolution to 8192x8192.
* Indicate if variable frame rate is detected in **Properties**.
* Added **Convert to Edit-friendly...** dialog when variable frame rate or non-seekable file opened.
* Added **Convert to Edit-friendly...** to **Properties** menu for video and audio files.
* Adding, removing, and adjusting **Fade In/Out** filters now updates fade controls on the **Timeline**.
* Major speed improvements for **Timeline** rendering, especially when changing zoom level.
* Stop showing waveforms on muted tracks.
* Fixed audio crackling on some systems.
* Fixed accuracy of reading and writing time values, particularly for non-integer frame rates.

##### Release 17.11

* Changed add-filter menu to be embedded instead of popup.
* Added **Master** label to **Timeline**.
* Show filters icon on track heads if track is filtered.
* Prioritize '0' shortcut for **Timeline** over **Playlist**.
* Do not adjust timeline zoom until slider is released.
* Added warning dialog to **Export** if file cannot be written (e.g. due to permissions).
* Added warning dialog to **Export** if chosen file is in the project.
* Added warning dialog to **Export** if the drive is low on space.
* Added Nepali translation.
* Added button to Text filter to insert the # symbol.

##### Release 17.10

* Fixed multi-threaded decoding with FFmpeg v3.2.
* Added 1080p 59.94 and 60 fps video modes.
* Added support for NVENC to Export panel.

##### Release 17.09

* Show in Folder now selects the file on Windows Explorer or macOS Finder.
* Renewed the code signing certificate for the Windows installer and executable.
* Updated SDL to v2.0
* Updated FFmpeg to v3.2
* Updated x264, x265, and vp8/9 to the latest stable versions.
* Added `--noupgrade` command line option and boolean General/noupgrade option to config/registry options.

##### Release 17.08

* Increased maximum **Timeline** zoom level.
* Increased **Speed** field precision to 3 decimal places.
* Increased maximum value for **Speed** field to 200x.
* Added Norwegian Bokmål translation.

##### Release 17.06

* Change maximum duration of a still image from 10 minutes to 4 hours.
* Added Hungarian translation.
* Fixed Chinese translation.

##### Release 17.05

* Fix opening and saving files on Windows with non-Latin characters in the name or path.
* Updated translations.

##### Release 17.04

* Fix crashing on launch on the new macOS 10.12.4.
* Added Japanese translation.
* Added Turkish translation.

##### Release 17.03

* Converted the track toggle buttons to icons.
* Now, you can press Del or Backspace to delete a selected item in the Recent panel.
* Playback now pauses at the out point in the Source player.
* Some stability improvements.
* Performance boost for Size & Position and Rotate filters on multi-CPU systems.

##### Release 17.02

* Fixed drag-n-drop from other than C: drive on Windows.
* Fixed '/' getting added to front of file paths on Windows.
* Fixed the MLT XML repair tool not correctly handling decimal point in some
  configurations.
* Fixed opening a network stream.
* Improved support for image sequences.
* Improved device capture.
* Added Slovenian translation.

##### Release 17.01

* Mostly just bug fixes.
* Added Chinese Taiwan translation.

##### Release 16.12

* Added **Constrained VBR** for the video codec rate control mode to Export.
* Added **Fixed** option to video **GOP** to Export.
* New audio mixing mode that does not affect levels.
* Increased usage of floating point for audio processing to improve quality.
* Added **Occitan** translation.
* More fixes for copying filters and LUT (3D) video filter.

##### Release 16.11

* Added **portable app** feature with **Settings > App Data Directory** and `--appdata` command line argument.
* Fixed drag-n-drop to Timeline after moving clip to different track.
* Fixed **LUT (3D) filter** for languages/regions that use comma for decimal point.
* Fixed **Properties > Speed** on macOS for languages/regions that use comma for decimal point.
* Added **Gaelic** (Scottish) translation.

##### Release 16.10

* Added **32-bit Windows** build.
* Changed Linux build to be more compatible.
* Added **LUT (3D)** video filter.
* Added **Lens Correction** video filter.
* Added **Merge with next clip** to Timeline clip context menu.
* Fixed **Paste Filters** for Timeline clips and tracks.
* Removed File > Open Other > Screen.

##### Release 16.09

* Added **Tiles**, **Icons**, and **Details** view modes to Playlist.
* Added **Copy Filters** and **Paste Filters**.
* Upgraded Qt to v5.6.1 with HiDPI support. (Set environment variable QT_AUTO_SCREEN_SCALE_FACTOR=0 to turn it off.)
* Converted some 16x16 icons to 32x32 for HiDPI.
* Moved the **Timeline Zoom** slider to the toolbar.

##### Release 16.08

* Added count-down (or up) generator: **File > Open Other > Count**
* Major performance boost for opaque clips on video tracks higher than **V1** with track **C**omposite enabled and **Blend mode: Over**.

##### Release 16.07

* Added **File** > **Export Frame...**
* Added **Remove transition** to **History** by trimming a neighboring clip to
  remove it.
* Fixed version checker.

##### Release 16.06

* Show red outline on scrub bar of **Source** player to indicate selection.
* Added **Cut**, **Copy**, and **Paste** to Edit menu and Timeline tool bar.
* Changed double-click on **Timeline clip** to select+seek instead of copying to **Source** player.
* Changed Timeline keyboard shortcut **A** to append.
* Changed Timeline keyboard shortcut **C** to copy.
* Changed Timeline keyboard shortcut **Enter** to seek to start of clip.
* Added **Peak** and **True Peak** meters to the **Audio Loudness** scope.
* Added version/upgrade-checker.
* Added check for missing files when opening .mlt XML project file.
* Added dialog to locate and resolve (relink) missing files in project file.
* For clips with speed changed, added support for saving and loading relative path and file names.
* Added **Export EDL** to the **File** menu.
* Added **YouTube** preset to **Export** (which does the same thing as not changing any export settings, not selecting an export preset, or clicking Reset).
* Updated Blackmagic Design SDI/HDMI output to work with recent driver updates.

##### Release 16.05

* Mostly just fixes.
* Added **Remove** to **Jobs** panel.
* Added **25%** option to player's **Zoom** button-menu.
* Improved application logging.
* Moved status messages front and central and removed status bar.


##### Release 16.04

* Fixed frequently reported problem with black video on Export.
* Fixed a few crashing bugs.
* Added an option to Windows installer to remove registry settings to help people with new crash-on-launch problems.
* Reduced memory usage when exporting a playlist or multitrack project.
* Added **Normalize: One Pass** audio filter (existing Normalize renamed **Normalize: Two Pass**.
* Added **Audio Loudness** to View > Scopes.
* Added **Brightness** video filter for CPU and GPU.
* Added **Contrast** video filter for CPU and GPU.
* Added **Reduce Noise** video filter for CPU only.
* Install ffplay and ffprobe executables.
* Improved visual feedback about what is selected in **Timeline**, **Properties**, and **Filters** views.
* Added **More Information** to clip Properties overflow-menu.
* Added **Start Integrity Check Job** to clip Properties overflow-menu.
* Added auto-rotate for video clips with orientation metadata.
* Added a Ukranian translation.

##### Release 16.03

* Changed player tab Program to **Project**.
* Changed panel name Encode to **Export**.
* Added a **From** field to the Export panel to allow exporting the project, a
  clip loaded in the **Source** tab of the player, or or each playlist item as a batch of jobs.
* Added an export preset for animated GIF.
* Upgraded FFmpeg to v3.0.
* Upgraded MLT to v6.0.0.

##### Release 16.02

-   Audio waveforms on timeline are updated incrementally as progress is made.
-   Allow dual pass encoding for CBR.
-   Added Show Video Thumbnails option to the timeline menu.
-   Added Rebuild Audio Waveform to a timeline clip's context menu.

##### Release 16.01

-   Added **Speed** parameter to Properties for an audio/video clip.
-   Added **Properties** views for track and timeline when selected.
    Click track head to select track; click the timeline's cornerstone
    (top left block) to select the timeline.
-   Added **Blend mode** to track properties (not available in GPU
    processing mode; only applies when compositing is enabled in the
    track header).
-   Added **Alpha Channel: View** video filter.
-   Added **Alpha Channel: Adjust** video filter.
-   Added **Chroma Key: Simple** video filter.
-   Added **Chroma Key: Advanced** video filter.
-   Added **Key Spill: Simple** video filter.
-   Added **Key Spill: Advanced** video filter.
-   And, as usual, a bunch of fixes and translation updates.

Note: none of the above, new video filters can utilize GPU-processing at
this time.

##### Release 15.12

-   Added crash recovery for untitled sessions.
-   Added Slovak translation.

##### Release 15.11

-   Added Rutt-Etra-Izer video filter.
-   Added audio/video device and screen capture for OS X.
-   Added screen capture for Windows.
-   Added Application Log to View menu.
-   Added Save button to text viewer dialogs (logs, XML).
-   Added video Deinterlace, Interpolation, and Parallel-processing
    options to Encode panel.
-   Reorganize the Settings menu and added headings.
-   Added Close action to File menu.
-   Added keyboard shortcuts for trimming on Timeline: I, Shift+I,
    O, Shift+O.
-   Added support for ripple trimming on Timeline.

##### Release 15.10

-   Mostly just bug fixes.
-   Added **Dutch** translation.
-   Added **Russian** translation.
-   Added project check and repair function.

##### Release 15.09

-   Added **Scrub Audio** to Settings menu.
-   Added **Display Method** to Settings menu (Windows only).
-   Added **Portugal Portuguese** translation.
-   Added **Mute** audio filter.
-   Updated Qt to v5.5.
-   Updated FFmpeg to v2.7.

##### Release 15.08

-   Added a Greek translation.
-   Added a **Ripple All Tracks** option to the Timeline menu.
-   4 new audio dynamics filters:
    -   Compressor
    -   Delay
    -   Expander
    -   Limiter
    -   Reverb

##### Release 15.07

-   4K UHD support
-   5 new video filters:
    -   Old Film: Dust
    -   Old Film: Grain
    -   Old Film: Projector
    -   Old Film: Scratches
    -   Old Film: Technocolor
-   5 new audio filters:
    -   Bass & Treble (3-band graphic equalizer)
    -   Band Pass
    -   High Pass
    -   Low Pass
    -   Notch
-   Added **Insert Track** and **Remove Track**.
-   New default Encode settings produce a better quality H.264 MP4 file.
-   Composite now defaults to on/enabled for new video tracks.

##### Release 15.06

-   Added 64-bit Windows build.
-   Added **Audio Spectrum** analyzer.
-   Changed audio **Gain** filter to use dB and log scale.
-   Added a toggle button to **Lock** a track.
-   Changed **Insert** and **Ripple Delete** to ripple across all
    unlocked tracks.
-   Changed keyboard shortcut to adjust track height to Ctrl+-
    and Ctrl+=.
-   Added keyboard shortcuts to toggle track:
    -   **Mute** - Ctrl+M
    -   **Hide** - Ctrl+H
    -   **Lock** - Ctrl+C

##### Release 15.05

-   Add **Distort** option to Size and Position filter.
-   Add video **Cut** option to Transition Properties.
-   Code-sign Windows executable and installer.
-   In Timeline, operate on clip under the play head if nothing
    is selected.
-   New keyboard shortcuts for Timeline:
    -   Select clip under play head: Ctrl+Space.
    -   Move selection one item to the right/left: Ctrl+Right/Left.
    -   Blanks can be selected to remove/ripple-delete: X or Shift+Del
        or Shift+Backspace.
    -   Deselect everything: Ctrl+D.
    -   Open As Clip: Enter/Return.

##### Release 15.04

-   Added an audio tone generator (in File > Open > Other).
-   Now you can set a new default duration for audio or video
    fade filters.
-   The WebM VP9 encode preset enables multi-threaded encoding.

##### Release 15.03

-   Add Update button to Playlist panel.
-   Double-clicking a successfully completed Encode job, now opens the
    result in Shotcut.
-   Consolidate GPU and Video filters in Filter menu.
-   Add View > Scopes > Audio Waveform.
-   Move audio peak meter to View > Scopes > Audio Peak Meter and
    main toolbar button.
-   Move volume slider to player toolbar icon.

##### Release 15.02

-   Add x265 codec.
-   Add video quality measurement tool.
-   No longer auto-plays upon opening a playlist or multitrack project.
-   Auto-select all text upon giving a timecode field focus.

##### Release 15.01

-   Only a few bug fixes and translation updates.

##### Release 14.12

-   New filter menu allows you favorite filters and see only favorites.
-   CPU-based video filters can be added after GPU-based filters.

##### Release 14.11

-   The HTML5 features are finally available on Windows!
-   Add source code editing to the HTML editor.
-   Add 3D Text filter based on WebGL, typeface.js, and three.js.
-   Add support for DirectShow devices on Windows in the Open
    Other dialog.
-   Add the [Opus audio codec](http://www.opus-codec.org/).
-   Change the VP9 WebM preset to use the Opus audio codec.
-   Add support for the \#localtime\# keyword to the Text filter (no
    button yet).
-   Restart instead of simply closing the app when changing the GPU or
    language settings.
-   Change the Redo keyboard shortcut to Ctrl+Y on Windows only.
-   Save file paths in MLT XML with relative names for assets in the
    same folder or sub-folder. This makes it easier to use a relocatable
    project folder.
-   Add scale and offset parameters and a preset widget to the
    Rotate filter. Usually after rotating a video, part of the image has
    been clipped. These new parameters provide control for that clipping
    processing including no clipping.
-   Add Italian translation.

##### Release 14.10

-   Maintenance release to fix some bugs.
-   Added Polish translation.
-   Restored FFV1 encoding and preset.
-   Change Leap Motion control: close hand to pause, open hand
    to shuttle.

##### Release 14.09

-   Added WMV and WMA encode presets.
-   Enabled the video player zoom and pan controls for OS X.
-   Added *Size and Position* video filter with a rectangle control that
    overlays the video player.
-   Added a simple *Text* video filter also with rectangle
    control overlay. This is a dynamic text filter supports pre-defined
    variables: *Timecode, Frame \#, File date, File name*.
-   Enabled parallel video processing for *Encode File* on systems with
    more than 2 logical cores when not using *GPU Processing*. This
    makes encoding faster when using filters, transitions,
    and compositing.
-   Added an *Opacity* <span style="background-color:
    transparent;"> video filter. </span>
-   Added an option on video fade filters: *Adjust opacity instead of
    fade with black*.
-   Now you can add filters to an entire track by clicking the track
    head and using the *Filters* panel.
-   New projects created with this version now load much more quickly.

##### Release 14.08

-   Now the Stabilize video filter really does work on Windows.
-   Added a Gamma menu item to the Settings menu when in GPU mode, which
    performs gamma correction. Previously, the display gamma was fixed
    at sRGB, but now you can choose Rec. 709. Previously, when applying
    a GPU filter, Shotcut would output sRGB gamma when encoding to a
    Y'CbCr file, and that has been removed/fixed.
-   Transfer characteristic (gamma) metadata is now written to video
    files that support it (e.g., H.264).
-   The filter UI layout now automatically adapts to a horizontal or
    vertical layout to suit more workspace layouts.
-   Upgraded FFmpeg to version 2.3.

##### Release 14.07

-   add "Remove Old Program Files" option to Windows installer
-   ask to exit if there are unfinished jobs
-   fix crash when loading invalid XML
-   add auto-save
-   fix frames repeating at end of some clips
-   fix Stabilize filter on Windows
-   add elegant combination slider and spinner control and revise all
    filter UIs to use it
-   cleanup all filter UIs to be consistent with other areas of UI
    panels
-   improve tooltips on timeline track headers
-   fix bug that gives you a MLT-XML GPU warning when the Balance or Pan
    filters are in a project
-   Save to app config the folder path name of last saved project XML.
    Then, use this path to default save dialogs such as next XML or
    video stabilization data.
-   On OS X, when using System theme, stack the display volume and mute
    toggles so these widgets do not appear so wide.
-   Workaround for the Stabilize filter's analysis job crashing on
    Windows.<br>The analysis job still crashes at the end, but
    the data is still created and usable. So, go ahead and try to use
    the data regardless of the job's failure.
-   Make adjusting image duration on timeline easier.<br>Now,
    the Duration field in Properties adjusts the out point, and the
    actual duration is 10 minutes. This lets you add just a few seconds
    to the Timeline by default but then stretch or shrink the image clip
    on the timeline up to 10 minutes. If you need more than 10 minutes,
    add the clip to the track again.

##### **Release 14.06**

-   upgrade x264 to git master and FFmpeg to v2.2
-   check compatibility of MLT XML with current GPU processing mode
-   introduce logging program activity to text file
-   more fixes for file names with extended characters on Windows
-   fix opening files with path/name with extended characters on Windows
-   upgrade to Movit 1.1.1 and replace GLEW with libepoxy

##### Release 14.05 and Earlier

-   14.04.29: fix crash on Windows w/GPU upon closing Color Grading
    filter UI
-   14.04.17: add Wave filter
-   14.04.14: fix huge memory leak introduced in v14.04.05 while working
    with interlaced clips with GPU Processing enabled
-   14.04.12: fix Overlay HTML filter appearing in filter list as
    Circular Frame
-   14.04.09: now provide 3 simultaneous color wheels for CPU-based
    Color Grading filter
-   14.04.08: add Catalan language
-   14.04.04: require shift key to make editing keyboard shortcuts
    target the playlist instead of the timeline
-   14.04.03: improved reliability for some FLV files and music with
    album art
-   14.04.01:
    -   restore Crop filter for GPU
    -   fix drag-n-drop from playlist to timeline
-   14.03.27: fix GPU processing on OS X
-   14.03.26:
    -   add GPU support for video wipe transitions
    -   fix aspect ratio of encoding on Windows in locales that use
        comma for decimal point (broken since 14.02.27)
-   14.03.25: GPU processing upgrades broke on OS X
-   14.03.24: add transition properties and video wipes
-   14.03.23: add transition by trimming
-   14.03.19: add resizing transition
-   14.03.17: display a time delta while moving, trimming, and fading on
    timeline
-   14.03.12: add initial support for cross-fade audio and video
-   14.03.11: add Open XML As Clip to File menu
-   14.03.09: in Encode, lock-down video parameters for presets that
    have specific resolution and framerate
-   14.03.07:
    -   add search for encode presets
    -   add Show Audio Waveforms toggle to timeline menu
-   14.03.02: add seeking to previous and next edit points using |<
    and >| buttons or alt+left/right keyboard shortcuts
-   14.03.01: add Fade In and Fade Out audio filters and Fade From Black
    and Fade To Black video filters with special timeline fader controls
-   14.02.27:
    -   more fixes for locales using comma for decimal point on Windows
    -   add a Set Default button for duration to the image properties
        panel
-   14.02.18:
    -   add insert and overwrite for drag-n-drop into timeline
    -   add option to scrub over timeline when dragging clips into
        timeline or within it
    -   show clip properties for selected shot on timeline
-   14.02.17: fix overwrite spanning multiple clips & gaps and undo for
    that
-   14.02.15: fix a luma (brightness) change when applying non-GPU
    filters
-   14.02.14: fix undoing a split
-   14.02.13:
    -   fix drag-n-drop from Source player to Timeline on Windows and OS
        X
    -   add keyboard shortcut 'S' to split clip under playhead on
        current track
-   14.02.12: fix encoding with GPU processing on Windows
-   14.02.11:
    -   fix GPU processing on Windows (where compatible)
    -   new video stabilization (
        [faster](http://public.hronopik.de/vid.stab/)) and audio
        normalization ( [EBU R128](https://tech.ebu.ch/loudness))
        filters <br>(video stabilization still crashes on
        Windows 8, but works for us on Windows 7 and other OS)
-   14.02.08: rework integration of playlist and timeline and change
    player tabs to Source / Program
-   14.02.05: add external monitoring on additional system monitor
-   14.02.04: track compositing fixes
-   14.02.03: fix crash on startup on Windows with dock title bars
    hidden
-   14.02.01:
    -   fix accuracy of edits when saving and loading project XML in
        locales with radix not a period
    -   set the UI locale from the language or host OS locale so that
        radix appears and interpreted correctly
    -   add Restore Layout to View menu
    -   add Show Title Bars to View menu
-   14.01.30: add Split At Playhead to context menu of clip on timeline
-   14.01.29: add saving and loading of playlist in a timeline project
-   14.01.28: upgrade FFmpeg libs to v2.1
-   14.01.27: reduce GPU memory usage with GPU processing
-   14.01.25: fix crash using audio only clip on Windows
-   14.01.23: fix inserting into playlist by menu or keyboard command
    (fix for OS X is in v14.01.24)
-   14.01.21: fix broken MP3 encode preset and sometimes wrong aspect
    ratio in encode
-   14.01.20: add Vignette and Diffusion (GPU only) filters
-   14.01.14: improve GPU processing performance
-   14.01.05 - 14.01.18: various timeline bug fixes
-   14.01.05: added insert and overwrite edits
-   14.01.02:
    -   fix GPU processing to work with Timeline
    -   re-enable GPU processing for Windows (still only partially works
        on some systems)
-   13.12.30:
    -   fix broken timeline on Windows
    -   fix putting Timeline panel in a tab stacked with other panels
    -   let Timeline panel be moved to top of window or floated
-   13.12.29: timeline broken on Windows
-   13.12.28: add multitrack timeline
-   13.12.26: fix OS X build broken since v13.12.21 due to Qt upgrade
-   13.12.22: upgrade Qt to version 5.2.0
-   13.11.21:
    -   fix process not completely closing on Windows
    -   fix broken keyboard shortcuts when not using English
-   13.11.18: add Invert and Sepia Tone video filters
-   13.11.17: add OpenGL version and extension test
-   13.11.15: add thumbnail caching
-   13.11.08:
    -   fix keyboard cursor left/right and page/up down (on Linux,
        issues still persist on Windows, OS X)
    -   add Stabilize video filter
    -   add Downmix audio filter
    -   add Swap Channels audio filter
-   13.11.06: add audio Normalize filter
-   13.10.31:
    -   add player zoom button
    -   broke keyboard cursor left/right and page up/down for navigating
        video (workaround: click on scrub bar to give it focus)
-   13.10.29: fix H.264 encoding on Windows - broken since 13.10.02
-   13.10.28: add Rotate video filter
-   13.10.21:
    -   fix encode when GPU is enabled (regression since 13.09.30)
    -   add DeckLink keyer capability
    -   add WebVfx producer widget so you can set HTML generator
        transparent (handy for keying HTML)
-   13.10.17: add audio Pan and Balance filters
-   13.10.16: fix loading tractor-based MLT XML files (e.g. from
    Kdenlive or OpenShot)
-   13.10.15: fix Leap Motion for Linux and Windows
-   13.10.11
    -   disable Leap Motion in Linux builds
    -   fix opening correct file from Recent search
    -   add first audio filters
-   13.10.10: conflict between QtWebKit and libLeap on Linux resulting
    in crash when loading HTML over HTTP
-   13.10.09: crashes in Recent panel when opening new (not in recent)
    file (downloads deleted since high visibility crash)
-   13.10.08: add search field to Recent panel
-   13.10.02 - 13.10.07: writes incorrect playlist
-   13.09.21: Best known version before Qt 5 upgrade
