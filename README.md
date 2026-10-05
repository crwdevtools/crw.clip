# crw.clip

**Find, review, and export standout moments from your local videos.**

crw.clip is a Windows desktop application for turning long recordings into a shortlist of clips. It combines audio energy, visual activity, and scene-change signals with hands-on reviewing, trimming, and framing tools. Media processing runs locally on your computer.

This repository contains **documentation only**. The application source code, executables, and user videos are not included. This documentation describes version **0.7.10**.

## Get started

1. Obtain the portable Windows executable from the developer's distribution channel and launch it. No Node.js installation is required; media tools are bundled.
2. Import a recording, open a saved project, or select a previous project on the welcome screen.
3. Click **Analyze video**. Use **Detection controls** to choose audio + visual, audio only, or visual only analysis.
4. Select suggestions in **Your moments** or on the **Source timeline**. Review them, adjust their boundaries, and give useful clips names or colours.
5. Choose **Export selected**, set the output resolution and quality, and choose where to save the MP4.

There is no application download hosted in this repository.

## Features

- Local audio, visual activity, and scene-change analysis with adjustable sensitivity.
- Up to **200 suggested clips**, ranked by signal strength.
- Keep, Reject, Reset, favourites, and review filters.
- Review mode with two seconds of surrounding context and automatic advancement after Keep or Reject.
- Manual clips, full-height timeline trim handles, precise IN/OUT controls, frame stepping, and playhead snapping.
- Undo/redo for clip edits; joining neighbouring clips and undoing joins.
- Source timeline zoom up to **100×**, mouse-wheel scrolling, Ctrl + wheel zoom, and adjustable height.
- A detailed **HH:MM:SS.mmm** ruler, scene markers, and visual activity indicators.
- Named and colour-tagged clips, score sorting, and colour filtering/sorting.
- Selecting a timeline clip reveals its matching sidebar card.
- Animated name flags for the selected clip, plus notches identifying other named clips.
- Live crop preview for **16:9**, **9:16**, and **1:1**, with horizontal and vertical framing controls.
- **720p, 1080p, and 2160p** MP4 exports, quality presets, and a cancellable export queue.
- Saved projects, autosave/recovery, and previous-project selection.
- Editable keyboard shortcuts and four colour themes: green, red, blue, and purple.

[Full feature reference](docs/FEATURES.md) · [User guide and shortcuts](docs/USER_GUIDE.md)

## Important limits

Detection measures signal changes, not the meaning of an event. Loud moments, motion, or scene cuts are suggestions to review, not guaranteed highlights. The score is a ranking indicator, not a confidence percentage.

Visual analysis samples two small frames per second, so brief activity between samples can be missed. H.264 MP4 is the most reliable preview format. Project files reference source videos; they do not embed them. Keep the original source available when reopening a project.

The app is still undergoing release testing. Validate an export before relying on it for a final delivery.

## Feedback

When reporting an issue, include the app version, Windows version, source format and duration, the steps to reproduce, and what you expected. Screenshots are helpful. Avoid sharing private footage or project files containing personal paths in a public issue.

This repository does not grant a licence to the application or publish its source code.
