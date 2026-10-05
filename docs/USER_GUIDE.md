# User guide

<img src="../assets/crwclip-icon.png" alt="crw.clip app icon" width="48" height="48">

[Return to README](../README.md)

## 1. Open a recording

Launch the portable Windows executable. Drop a local video onto the welcome screen or browse for one. You can also open a saved `.clipproject` file or choose a previous project.

Common import extensions include MP4, MKV, MOV, WEBM, and AVI. Successful preview depends on the codecs inside the file; use H.264 MP4 when possible.

![Welcome screen: import a video or reopen a previous project](../assets/screenshots/start-screen.png)

## 2. Find moments

Click **Analyze video**. Open the settings icon beside **Your moments** to adjust:

- **Analysis mode:** Audio + visual, Audio only (faster), or Visual only.
- **Audio and visual sensitivity:** Higher settings find smaller changes.
- **Suggestion limit:** Request between 1 and 200 new suggestions.
- **Minimum event duration:** Ignore brief events.
- **Minimum/maximum clip duration:** Control suggestion lengths.
- **Before/after padding:** Include context around detected events.

Use **Apply cached signals** to rerank existing analysis when the required signals are available. Changing analysis modes may require a new scan. Re-analysis preserves manual, reviewed, favourite, named, and colour-tagged clips; their existing scores may remain unchanged. New suggestions avoid overlapping each other and preserved clips, so the requested count is a limit, not a guarantee.

Scores favour stronger audio changes and visual activity. A scene change alone does not establish that a moment is interesting.

## 3. Review and organise

Click a clip card or a timeline highlight to select it. Timeline selection reveals the matching sidebar card; filters clear only if they hide that clip.

Use **Keep**, **Reject**, or the reset icon. Favouriting a clip also marks it Keep. You can filter by review state or favourites, sort by score, and expand **Tags & sorting** for colour controls.

Choose **Review mode** to work through unreviewed clips in source order. Each preview includes up to two seconds before and after the clip. Keep or Reject advances to the next unreviewed clip. Review stops when all clips have decisions. The extra preview context is not added to exported clip boundaries.

### Names and colours

Use **Clip name** on a card to rename it. Exported files use that name, with filename-safe substitutions and suffixes where needed to avoid collisions.

The eyedropper opens the colour picker; right-click it to clear the colour. A chosen colour overrides the theme for the timeline highlight and name flag. Named, unselected clips show a small notch below the highlight. Selecting one opens its full name flag with a 3 px gap.

## 4. Trim and navigate

Select a clip, then drag either timeline edge at any point along its height. A precise time readout appears during the drag. Edges snap near the playhead; hold **Alt** to bypass snapping.

In **Clip Controls**, enter IN/OUT times in seconds, set boundaries at the playhead, or use **Extend IN / Extend OUT** to add one second before/after the clip. Invalid or zero-length ranges are prevented.

- **Wheel:** Scroll the source timeline when zoomed in.
- **Ctrl + wheel:** Zoom the timeline; the modifier can be changed in the hotkey editor.
- **Jump to selected:** Bring the selected range into the timeline viewport.
- **Timeline height:** Change the highlight/waveform height.
- **Selected clip / Full source:** Change playback bounds.
- **Loop clip:** Repeat selected-clip playback outside review mode.
- **Frame buttons:** Step through the video one frame at a time.

Use **Mark manual clip** to create a clip around the playhead. Manual clips can intentionally overlap.

### Undo, joining, and removal

Use Undo/Redo or their keyboard shortcuts for clip edits. Undo history is session-based, holds up to 100 changes, and resets when another video/project is loaded. A trim drag is one undo step.

Expand **Join clips** in Clip Controls to join the previous or next chronological clip. The resulting range includes any gap, uses the selected clip's framing, and is marked Keep. **Undo last join** restores the originals. Recorded join history is stored in saved projects.

**Remove selected** deletes a clip from the moments list. Undo or **Undo remove** can restore it during the session. Re-analysis may suggest a removed moment again.

## 5. Frame the output

Select **16:9**, **9:16**, or **1:1** under Output shape. Use the horizontal and vertical Position sliders, or **Centre crop**, to frame the clip. The output monitor previews the crop; **Show source** displays the uncropped source.

## 6. Export

Click **Export selected**, then choose:

- Resolution: **720p, 1080p, or 2160p**.
- Quality: **High quality, Balanced, or Smaller file**.
- Optional **Also export all kept clips**.

Without the checkbox, choose a file location for the selected clip. With it, choose a folder for the selected clip plus all kept clips. The selected clip is included once, and does not need to be marked Keep. Exporting does not change review decisions.

Exports are H.264 video with AAC audio when available, in MP4 files. The queue shows individual and overall progress. Cancelling preserves completed clips and removes unfinished output. Higher output resolutions do not restore detail absent from the source.

## 7. Save your work

Use **Save project** to save edit decisions and analysis. Autosave also maintains session recovery, and the welcome screen offers previous projects. Source videos are not copied into projects. Keep the original video at its saved path.

## Default shortcuts

Change these under **Edit → Hotkey editor**. Existing customised shortcuts may differ. While typing in a field, normal text editing takes precedence.

| Action | Default |
| --- | --- |
| Play / pause | Space |
| Seek 1 second | Left / Right arrow |
| Seek 5 seconds | Shift + Left / Right arrow |
| Previous / next frame | Comma / Period |
| Mark manual clip | M |
| Set IN / OUT at playhead | I / O |
| Keep / Reject / Reset | K / R / U |
| Remove selected | Delete |
| Undo / Redo | Ctrl + Z / Ctrl + Shift + Z |
| Undo join | Ctrl + J |
| Jump to selected | F |
| Zoom in / out | Ctrl + = / Ctrl + - |
| Export selected | Ctrl + E |
| Save / Open project | Ctrl + S / Ctrl + O |
| Timeline wheel zoom | Ctrl + mouse wheel |

## Troubleshooting

**Preview cannot decode:** Try an H.264 MP4 source. Importable file extensions do not guarantee preview codec support.

**Too few suggestions:** Raise sensitivity, reduce the minimum event duration, or try combined analysis. Preserved clips and overlapping candidate ranges can reduce the count.

**A project cannot find its video:** Restore the source to its original saved path. Projects do not include the source footage.

**Unexpected crop:** Switch back to output preview and check the aspect ratio and Position sliders before exporting.

**A score did not change after re-analysis:** Reviewed, manual, favourite, named, or colour-tagged clips are preserved. New unreviewed suggestions use the current scoring.
