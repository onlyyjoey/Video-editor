# Video-editor

**Open: https://onlyyjoey.github.io/Video-editor/**

A Premiere-style video editor (a modified copy of the open-source [FilmCraft](https://github.com/storytold/filmcraft)) set up for phones like KineMaster and CapCut.

- **Portrait:** the video on top and the timeline below with the playhead fixed in the middle (drag the timeline to scrub). Tools run along the bottom, and selecting a clip shows its clip tools.
- **Landscape:** a tool strip down the left side, with video controls on the right of the video.
- **Media:** swipe in from the left edge to open your media, then tap a file or drag it onto the timeline.
- **Keyframe tool:** sliders for Scale, Position, Rotation and Opacity. You can also drag or pinch the video to keyframe it.
- **Fill:** fills a landscape clip's black bars with a blurred copy of the clip.
- **Gestures:**
  - long-press opens a menu
  - pinch zooms
  - two-finger tap is undo, three-finger tap is redo

Media stays on your phone.

On iPhone: open the link in Safari → Share → **Add to Home Screen**.

## How it's built

- `source/` holds the editor's source code (Rust → WebAssembly).
- `docs/` holds the built app, which GitHub Pages serves (Settings → Pages → Deploy from a branch → `main` / `/docs`).
- Any push that changes `source/` runs the **Build FilmCraft web app** workflow.
  - If only the touch layer (`source/apps/filmcraft-web/web/`) changed, it takes about a minute.
  - Otherwise it recompiles the editor, which takes about 15–25 minutes.
