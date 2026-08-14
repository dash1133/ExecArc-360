# ARC Demo Video Kit

Everything needed to re-render or modify the ARC client demo video (3:19, 1920×1080 MP4, AI voiceover).

## Folder map

```
ARC_Demo_Video_Kit/
├── video/ARC_Demo_Video.mp4      ← the current final video
├── docs/
│   ├── ARC_Narration_Script.md   ← storyboard + narration per scene
│   └── ARC_Video_Transcript.md   ← verbatim transcript with timestamps
├── src/
│   ├── generate_voiceover.py     ← makes the narration audio (edge-tts)
│   └── render_video.py           ← draws every frame + encodes the MP4
├── assets/
│   ├── fonts/                    ← bundled fonts (render looks the same everywhere)
│   ├── vo/*.mp3                  ← current voiceover, one file per scene
│   └── timeline.json             ← scene durations derived from the voiceover
└── build/                        ← created on first run (frames, temp audio)
```

## Requirements

- Python 3.9+ with two packages: `pip install pillow edge-tts`
- `ffmpeg` on PATH (https://ffmpeg.org)
- Internet is only needed for `generate_voiceover.py` (Microsoft edge-tts). Rendering is fully offline.

## How to render

```
python src/render_video.py
```

Output: `ARC_Demo_Video.mp4` in the kit root. First run takes several minutes (it draws ~4,800 frames). Frames are cached in `build/frames/` — re-runs only draw what changed. **After editing visuals, delete `build/frames/` first** so stale frames are re-drawn. In time-limited shells you can pass a budget in seconds (`python src/render_video.py 300`) and re-run until it prints `ALLDONE`.

## Common changes

**1. Change the narration**
Edit the `SCENES` text in `src/generate_voiceover.py`, then:
```
python src/generate_voiceover.py    # regenerates audio + timeline into build/
rm -rf build/frames                 # scene lengths changed, redraw all
python src/render_video.py
```
Scene lengths adapt automatically to the new audio. Voices: change `VOICE` (e.g. `en-US-JennyNeural`, `en-GB-RyanNeural`); list all with `python -m edge_tts --list-voices`.

**2. Change on-screen text (titles, bullets, callouts)**
All per-stage copy lives in the `STAGES` dict in `src/render_video.py`: title, subtitle, bullet list, and callouts. Each callout is `(start_frac, end_frac, (x0, y0, x1, y1), "label")` — times as fractions of the scene, box as fractions of the mockup screen.

**3. Change the UI mockups**
The mock screens are drawn in `mock_s1()` … `mock_s7()` in `src/render_video.py` (names, roles, competencies, goals, etc. are plain strings). To use **real product screenshots** instead: load a PNG in place of a `mock_sX` function and return it resized to the same `(w, h)` — everything else (shadow, slide-in, callouts) keeps working.

**4. Change branding**
Colors are at the top of `src/render_video.py` (`BG`, `INK`, `ACC` per stage). The ARC logo is drawn in `logo_img()`. Fonts are swappable in `assets/fonts/` (keep the filenames).

**5. Resolution / fps** — `W, H, FPS` at the top of `src/render_video.py`.

## How it works (30 seconds)

`generate_voiceover.py` creates one MP3 per scene and writes `timeline.json` with each scene's duration (voice + 0.7 s lead-in + 1 s tail). `render_video.py` reads that timeline, draws every frame with Pillow (scene layouts, eased animations, highlight callouts, the 7-step progress rail), pads each scene's audio to exactly the video length, and encodes with ffmpeg — so voice and visuals stay in sync no matter what you change.
