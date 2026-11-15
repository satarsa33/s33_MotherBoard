# S33 - Mother Board

A **modular studio in the browser** that gathers the S33 family in one place: synths, drum machine, effects, looper and MIDI tools become modules on a board, wired together with audio, MIDI and clock cables.

Made for **Chrome on the Mac** with a MIDI keyboard and Logic Pro. It is a **PWA** in a single HTML file, with no dependencies: every instrument is embedded and runs on one shared audio engine.

> A personal project of the S33 family. The full user manual, in Italian, is in [LEGGIMI.txt](LEGGIMI.txt). Current version: **0.21**.

---

## Modules

| Group | Modules |
|---|---|
| Instruments | **Twin Core** (semi-modular mono), **Nostos One**, **Vega** (8-voice poly, Juno style), **Acid** (303-style bass line with 16-step sequencer), **Hexa** (6-operator FM, DX7 style, `.syx` banks), **Drum Machine L02** (10 voices, 8 patterns), **Granular**, **JSB**, **FM-1** (hardware synth over USB) |
| Effects | **Stompbox**, **Looper** (4 cassette tracks, 4 inputs, overdub, undo, WAV mixdown) |
| MIDI | **MIDI In**, **MIDI In 2**, **MIDI Out**, **MIDI Split** (8 channels), **Chords** (chords and arpeggiator) |
| Services | **Clock** (internal or Logic MIDI clock), **Mixer**, **Output** (with WAV recording), **Audio In** (audio interface / microphone) |

## Features

- **Board and Patches**: the board shows the live signals (levels, notes, clock beats); Patches is the cable view, drag from socket to socket. Obvious cables are made automatically when a module is added
- Click a module to open the real instrument full screen (Esc to return)
- **Logic Pro friendly**: MIDI clock follow, notes played at the time Logic sent them (adjustable TIMING look-ahead), All Notes Off, loop protection, MIDI Split by channel over the IAC bus
- **Audio In** with channel select, gain, VU meters and latency compensation for the Looper
- **Sessions**: New, Open, Save to file, including every instrument's settings; Looper tapes saved at full quality with the **TAPES** option
- **PANIC** closes every note on every module

## Quick start

1. Open `index.html` in **Chrome**.
2. Click once to start the audio and allow MIDI access.
3. Add modules from the list, or start from a ready-made set (Synth & FX, Groove) or the last session.

### Install as an app

```bash
cd v0.21
python3 -m http.server 8033
# open http://localhost:8033 in Chrome → ⋮ menu → Install S33 - Mother Board
```

Browser storage is per address: settings and sessions opened as a file, from `localhost` or from GitHub Pages are kept separately. Use **Save / Open** of a session to move your work.

### Publish on GitHub Pages

Upload **the contents** of the version folder (`index.html`, `sw.js`, `manifest.webmanifest`, `icons/`, `README.md`, `LEGGIMI.txt`), then *Settings → Pages → Deploy from a branch →* `main` / `(root)`. All paths are relative. After publishing a new version, change `VERSIONE` in `sw.js`.

## Folder structure

```
index.html              the Mother Board, with every instrument embedded
manifest.webmanifest    PWA manifest
sw.js                   service worker (offline cache)
icons/                  app icons
README.md               this file
LEGGIMI.txt             user manual and version history (Italian)
```

The build sources (templates and module scripts) live in the project's `build/` folder, not in the published version; the rebuild commands are at the end of `LEGGIMI.txt`.

## Use

Personal project, free to study and modify. No warranty of any kind.
