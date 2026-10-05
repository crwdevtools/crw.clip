# Feature reference

[Return to README](../README.md) · [User guide](USER_GUIDE.md)

| Area | Included features |
| --- | --- |
| Import | Local recordings; saved project files; previous-project selection |
| Analysis | Audio energy, visual activity, scene changes; combined/audio/visual modes; cancellable scanning |
| Detection controls | Audio/visual sensitivity; 1–200 suggestion limit; event duration; clip length; before/after padding; cached-signal re-ranking |
| Reviewing | Keep, Reject, Reset, favourites, review filters, bulk Keep unreviewed |
| Review mode | Source-order unreviewed playback; up to 2s context on each side; automatic advance after Keep/Reject |
| Sidebar | Editable names, colour dropper, score meters, score sorting, colour filtering/sorting, timeline-selection reveal |
| Timeline | Audio waveform, visual activity, scene markers, HH:MM:SS.mmm ruler and minor notches, up to 100× zoom, wheel scrolling, configurable modified-wheel zoom, adjustable height |
| Timeline labels | Selected-only animated full-name flags; 3px separation; notches for other named clips; clip-specific colour overrides |
| Trimming | Full-height edge handles, live time readout, playhead snapping with Alt bypass, numeric IN/OUT fields, set boundaries at playhead, one-second extensions |
| Clip management | Manual clips, chronological joins including gaps, undo joins, removal/restoration, session undo/redo |
| Preview | Selected clip/full source modes, loop, frame stepping, volume, expandable preview, source/output switch |
| Framing | Live crop preview; 16:9 / 9:16 / 1:1; horizontal and vertical positioning; centre crop |
| Export | Selected clip or selected + kept batch; named MP4 files; 720p / 1080p / 2160p; three quality presets; queue progress and cancellation |
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
