# crw.clip

<p align="center">
  <img src="assets/crwclip-logo.svg" alt="crw.clip crow logo" width="96" height="96">
</p>

**Find, review, reframe, and export standout moments from your local videos.**

crw.clip is a Windows desktop application for turning long recordings into a shortlist of clips. It combines local audio energy, visual activity, and scene-change analysis with precise review, trimming, and gameplay/facecam layout tools.

This repository contains **documentation and preview images only** for **v0.7.25**. Application source code, executables, and user videos are not included. Obtain the portable Windows executable from the developer's distribution channel. No Node.js or Python installation is required, and media tools are bundled.

## App preview

Preview images were captured in v0.7.24 and show the workflow available in v0.7.25.

### Clip review workspace

![crw.clip v0.7.24 workspace with colour-tagged clips, output preview, and source timeline](assets/screenshots/workspace-v0.7.24.png)

Review named and colour-tagged moments, trim their boundaries, and frame the output in one workspace.

### Gameplay & facecam layouts

![crw.clip v0.7.24 gameplay and facecam layout editor](assets/screenshots/layout-v0.7.24.png)

Choose source regions, arrange output sections, and adjust framing, styling, keyframes, or saved presets.

### Welcome screen

![crw.clip v0.7.24 welcome screen with video import and session recovery](assets/screenshots/welcome-v0.7.24.png)

Import a recording, reopen a saved project, or resume a recovered session.

## Updates in v0.7.25

- Manual timeline trimming keeps the clip highlight in place vertically. The floating time readout no longer changes the surrounding layout during dragging.
- Version labels follow the application version, and documentation describes the current workflow.

## Get started

1. Launch the portable Windows executable and import a recording or open a project.
2. Click **Analyze video**, or open **Detection controls** to choose combined, audio-only, or visual-only analysis.
3. Select suggestions in **Your moments** or on the **Source timeline**. Keep/reject them, trim boundaries, and add names or colours.
4. Choose an output shape or open **Layout** to arrange gameplay and facecam for the selected clip.
5. Click **Export selected**, choose resolution and quality, and save an MP4. Optionally include all kept clips.

There is no application download hosted in this repository.

## Features

- Local audio, visual activity, and scene-change analysis, adjustable sensitivity and up to **200 suggestions**.
- Detection controls popout with Analyze, Re-analyze, and **Apply cached signals**.
- Keep, Reject, Reset, favourites, review filters, and source-order review with surrounding context.
- Compact moments cards that expand when selected, names, colour tags, score meters, and timeline/sidebar selection linking.
- Stable timeline resizing with a floating trim readout, precise trimming, frame stepping, IN/OUT controls, playhead snapping, manual clips, joins, and undo/redo.
- Source timeline zoom up to **100×**, mouse-wheel scrolling, modified-wheel zoom, adjustable height, and a detailed **HH:MM:SS.mmm** ruler.
- Animated selected-clip name flags and clip-specific colour styling.
- Live source/output previews, click-to-play/pause, continuous scrubbing, and remembered **25%, 50%, 75%, or 100%** preview quality.
- **Original source, 16:9, 9:16, 1:1, 21:9, 32:9, and 4:3** output shapes.
- Gameplay/facecam layouts with draggable source regions and output boxes, centre snapping, Fit/Fill, linked resizing, aspect-ratio lock, and independent source zoom/pan.
- Saved layout presets, copy-to-multiple-clips, editor undo/redo, manual framing keyframes, borders, rounded corners, background styling, and safe-area guides.
- **Original source, 720p, 1080p, and 2160p** MP4 exports, named files, quality presets, and a cancellable export queue.
- Saved projects, autosave/recovery, recent projects, and a clear-recent-list button.
- Editable keyboard shortcuts and green, red, blue, and purple themes.

[Full feature reference](docs/FEATURES.md) · [User guide and shortcuts](docs/USER_GUIDE.md)

## Preview performance

Lower preview quality prepares smaller local H.264 preview files with frequent keyframes for seeking. Proxies are cached and reused. 100% restores the original. The original remains available during preparation, which pauses during analysis/export. Exports and analysis always use the original video.

Paused previews no longer redraw continuously. Blurred backgrounds are reused during styling/placement edits. Timeline pointer updates are coalesced to display frames, unchanged cards and signals skip repeated rendering, and analysis uses fixed-size raw buffers and packed signal blocks.

## Scope and limits

Detection measures signal changes, not the meaning of an event. Loud moments, motion, and scene cuts are suggestions to review, not guaranteed highlights. Scores are ranking indicators, not confidence percentages. Visual analysis samples two small frames per second, so brief activity can be missed.

Framing keyframes are manual, not automatic object tracking. Project files reference source videos rather than embedding them. Keep the original available. Preview proxies take time and disk space to prepare. Older proxies are removed toward a 2 GiB budget, with the newest prepared proxy retained even if larger. Compact analysis signals still grow with recording duration.

## Feedback

When reporting an issue, include the app version, Windows version, source format and duration, steps to reproduce, and expected behaviour. Avoid posting private footage or personal file paths in public issues.

This repository does not grant a licence to the application or publish its source code.
