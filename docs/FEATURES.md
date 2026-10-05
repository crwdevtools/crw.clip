# Feature reference — v0.7.24

[Return to README](../README.md) · [User guide](USER_GUIDE.md)

| Area | Included features |
| --- | --- |
| Import | Local recordings; saved project files; previous-project selection; clear recent list without deleting projects/videos |
| Analysis | Audio energy, visual activity, scene changes; combined/audio/visual modes; cancellable scanning |
| Detection controls | Audio/visual sensitivity; 1–200 suggestion limit; event duration; clip length; before/after padding; cached-signal re-ranking; movable/resizable controls popout |
| Reviewing | Keep, Reject, Reset, favourites, review filters, bulk Keep unreviewed |
| Review mode | Source-order unreviewed playback; up to 2s context on each side; automatic advance after Keep/Reject |
| Sidebar | Selected-only expanded cards, editable names, clip-coloured selections and field focus, colour dropper, score meters, score sorting, colour filtering/sorting, timeline-selection reveal |
| Timeline | Audio waveform, visual activity, scene markers, HH:MM:SS.mmm ruler and minor notches, up to 100× zoom, wheel scrolling, configurable modified-wheel zoom, adjustable height |
| Timeline labels | Selected-only animated full-name flags; 3px separation; notches for other named clips; clip-specific colour overrides |
| Trimming | Full-height edge handles, live time readout, playhead snapping with Alt bypass, numeric IN/OUT fields, set boundaries at playhead, one-second extensions |
| Clip management | Manual clips, chronological joins including gaps, undo joins, removal/restoration, session undo/redo |
| Preview | Selected clip/full source modes, loop, frame stepping, volume, expandable preview, click-to-play/pause, live scrubbing, source/output switch, remembered 25/50/75/100% quality and cached preview proxies |
| Framing | Live crop preview; Original source / 16:9 / 9:16 / 1:1 / 21:9 / 32:9 / 4:3; horizontal and vertical positioning; centre crop |
| Gameplay/facecam | Per-clip layouts; independent source/output regions; centre snapping; Fit with blur / Fill section; linked section resizing; aspect-ratio lock; source zoom/pan; separate resets; saved presets; copy to multiple clips; editor undo/redo; manual pan/zoom keyframes |
| Layout styling | Adjustable blur/brightness or solid backgrounds; per-layer borders/colours/rounded corners; preview-only safe-area guides; compact Framing/Style/Keyframes/Presets tabs |
| Performance | Local lower-resolution H.264 proxies; frequent seek keyframes; cache reuse/eviction/cancellation; idle redraws removed; up to three cached blur surfaces per video; frame-coalesced timeline interaction; memoised signals/cards; fixed-size analysis buffers and packed signal blocks |
| Export | Selected clip or selected + kept batch; named MP4 files; Original source / 720p / 1080p / 2160p; three quality presets; queue progress and cancellation |
| Projects | Save/open `.clipproject`; autosave/recovery; recent projects; saved clip names, colours, framing and review decisions |
| Personalisation | Editable hotkeys; green/red/blue/purple themes; theme-aware logo and scrollbars; reduced-motion flag support |

## Scope and limitations

- Processing happens locally; no online highlight model is required.
- Detection is heuristic, not semantic recognition or object tracking.
- Visual analysis uses two small frames per second.
- Scores compare signal strength; they are not probabilities or confidence percentages.
- Manual edits may overlap; generated suggestions avoid existing preserved ranges.
- Review context changes playback only, not export boundaries.
- Source footage must remain available for saved projects.
- Native Windows playback and release behaviour should be checked on the target system.

## Preview cache and processing

Preview quality scales width and height: 50% means one quarter of the source pixels. Proxies are prepared on first use, keyed by source path, size, modification time and quality, and remain local. Preparation uses two encoding threads and pauses during analysis/export. Cache eviction aims for 2 GiB while retaining the newest prepared proxy. Exports and detection read the original source.

Raw analysis buffers have fixed sizes; retained compact signals still grow with recording duration. Progress updates are throttled during scanning. These optimisations do not establish a specific speed or memory advantage on every recording.
