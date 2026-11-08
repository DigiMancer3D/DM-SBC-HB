# DigiMancer Streamer Apps
### DM SBC Resource Hub

**A single place to discover, install, and coordinate the DigiMancer3D local-first streamer toolkit.**

Low-resource • Local-first • OBS-friendly • VTuber-ready • Linux-focused (with notes for other platforms) • Extensible

This repository is the **Resource Hub** for the DigiMancer streamer application suite.  
It collects the individual tools (most of which live in their own repositories) into one navigable overview, recommended install order, and coordination notes.

> **Note:** There is already a parent hub at [DigiMancer3D/DMST](https://github.com/DigiMancer3D/DMST).  
> This SBC Resource Hub is intended as a focused, living collection point you can expand as new tools (including ones not yet public) are added.

---

## Quick Start (Recommended Layout)

Create a dedicated folder and clone the tools you need:

```bash
mkdir -p ~/SBC_Streamer_Apps
cd ~/SBC_Streamer_Apps
```

Then clone individual apps (or use submodules later if you turn this into a monorepo).  
Most tools are pure Python + Tkinter and run well in a venv.

---

## The Tool Suite

| Order | Tool | Repository / Location | Status | Role |
|-------|------|-----------------------|--------|------|
| 1 | **Streamer Board & Console** | [Streamer-Board-Console](https://github.com/DigiMancer3D/Streamer-Board-Console) | Public | Central command console: app adapters, Studio Profiles, Pin Boards (`.sboard`), hotkeys, resource monitoring, coordinated launches. |
| 2 | **DMS Live Switcher** | [DMS-Live-Switcher](https://github.com/DigiMancer3D/DMS-Live-Switcher) | Public | Independent live control panel with dual rails for switching Streamer Board pinboards and Deck Card Widget cards without opening full editors. |
| 3 | **Deck Card Widget** | [Deck-Card-Widget](https://github.com/DigiMancer3D/Deck-Card-Widget) | Public | Private controller + clean OBS output window for deck cards, claims, sources, emoji/PNG/text layers, `.buttstore` persistence. |
| 4 | **Bitninja Mocap Lite** | [Bitninja-Mocap-Lite](https://github.com/DigiMancer3D/Bitninja-Mocap-Lite) | Public | OBS-focused local VTuber mocap fork of SysMocap. Low-latency VRM tracking, local model loading, optional HTTP/WebSocket output. |
| 5 | **SWAR** (Script Writer and Reader) | [3DChangesPerspectives/SWAR](https://github.com/DigiMancer3D/3DChangesPerspectives/tree/main/SWAR) | Public (inside 3DCP repo) | Writer + immersive Reader for `.script`, Markdown, `.txt`, and Story Arc (`.arcs`) files. Live preview, teleprompter, themes. |
| 6 | **Sound Card** | [soundcard](https://github.com/DigiMancer3D/soundcard) | Public | Real-time microphone visualizer: living physics blob + vocal EQ bars + Super Saiyan power-up mode. OBS chroma-key friendly. |
| 7 | **G502 Visualizer** | [G502V](https://github.com/DigiMancer3D/G502V) | Public | Real-time Logitech G502 HERO button / scroll / tilt / G-Shift visualizer with direction indicator. Perfect for OBS overlays. |
| 8 | **soloPAW** (Profile Switcher + Controller Map Studio) | [soloPAW](https://github.com/DigiMancer3D/soloPAW) | Public | One-handed / dense mouse-first control system. Includes stream-safe Profile Switcher (to change active setups) and WYSIWYG Controller Map Studio. Built around G502 but adaptable. |
| 9 | **FGF** | — | Not yet public | Placeholder for future tool. |

You can install only the pieces you need. The Streamer Board & Console is designed to orchestrate the others via adapters and Studio Profiles.

---

## How the Pieces Fit Together

```text
Streamer Board & Console  ←→  DMS Live Switcher
         │                          │
         ├── Pin Boards (.sboard)   ├── Deck cards
         ├── App Adapters           └── Quick live switching
         ├── Studio Profiles
         │
         ├── Deck Card Widget (OBS output window)
         ├── Bitninja Mocap Lite (VRM / camera)
         ├── SWAR (scripts / teleprompter)
         ├── Sound Card (mic visualizer)
         ├── G502V (mouse visualizer)
         └── soloPAW Profile Switcher (which control layout is active)
```

- **Streamer Board & Console** is the hub for launching, parking, and profiling tools.
- **DMS Live Switcher** gives a dedicated, always-available live control surface for pinboards and deck cards.
- **soloPAW Profile Switcher** lets you change which dense control map / streamer setup is active without leaving the stream.
- Everything is local-first. No required accounts or cloud services.

---

## Installation Notes

Most tools follow a similar pattern:

```bash
git clone https://github.com/DigiMancer3D/<Repo>.git
cd <Repo>
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt   # or the specific packages listed in each README
python3 <main_script>.py
```

- Prefer a shared parent folder (`~/SBC_Streamer_Apps`) so paths stay consistent for adapters.
- Many tools include `setup_*.sh` or `doctor_*.sh` scripts — run those first when available.
- OBS setup is almost always: Window Capture of the dedicated output window (titles are stable).
- Bitninja Mocap Lite is Electron/JavaScript-based; the others are primarily Python/Tkinter.

---

## Recommended Starting Order

1. Streamer Board & Console  
2. Deck Card Widget  
3. DMS Live Switcher (to control the above live)  
4. Bitninja Mocap Lite (if doing VTuber)  
5. Sound Card + G502V (visualizers)  
6. SWAR (scripting / teleprompter)  
7. soloPAW Profile Switcher + Controller Map Studio (control layouts)

---

## Related Projects

- [.script format](https://github.com/DigiMancer3D/.script) — the public plain-text script markup used by SWAR  
- [DMST](https://github.com/DigiMancer3D/DMST) — earlier unified parent hub with detailed install & workflow docs  
- [3DChangesPerspectives](https://github.com/DigiMancer3D/3DChangesPerspectives) — home of SWAR and show visual archive  

---

## Philosophy

- Local-first and offline-capable  
- Low resource usage (Tkinter / pure Python where possible)  
- OBS-friendly dedicated output windows  
- Modular — use one tool or the whole suite  
- Designed around one-handed / accessibility-conscious workflows (soloPAW lineage)  
- Extensible via adapters and simple file-based state

---

## Status & Future

This Resource Hub is a starting point. As new tools (including FGF and others) are published, they will be added here.

Feel free to treat this repository as a monorepo later by adding the other repos as git submodules if you want everything in one clone.

---

**Creator:** DigiMancer3D (@Z0M8I3D)  
**Website:** [3Dthe.ninja](https://3Dthe.ninja)  
**License:** Most tools are BSD-3-Clause or GPL-3.0 — check individual repositories.

---

*Last reviewed from public GitHub state (DigiMancer3D) — ready for expansion.*
