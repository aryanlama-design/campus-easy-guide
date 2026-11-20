[project_readme.md](https://github.com/user-attachments/files/35186036/project_readme.md)
# 🧭 Campus Easy Guide — Accessible Campus Navigator (LPU)

An inclusive, WCAG AAA high-contrast campus navigation web application designed to help students—including wheelchair users and visually impaired individuals—navigate university campuses safely and independently. Built around a Lovely Professional University (LPU) campus graph, it supports step-free routing, real-time hazard rerouting, spoken landmark guidance, and multilingual voice control.

---

## ✨ Key Features

- **♿ Mobility-Aware Routing (Dijkstra Engine):**
  - **No Stairs (Wheelchair Mode):** Strictly filters out stairs and unaccessible entrances, prioritizing 1:12 ramps and working elevators.
  - **Audio Guide (Visually Impaired Mode):** Prioritizes paths with tactile paving and provides rich sensory & audio landmarks at every step.
  - **Fastest Mode:** Finds the shortest walking time regardless of stairs.
- **🎙️ Multilingual Voice Control & TalkBack Reader:**
  - Supports **English (`en-IN`)**, **Hindi (`hi-IN`)**, and **Punjabi (`pa-IN`)** with automatic language detection.
  - Understands natural commands such as *"From Main Gate to Block 38"*, *"Block 34 se Food Court jana hai"*, *"Start route"*, *"Lift kharab hai"*, and *"Describe map"*.
  - Built-in **TalkBack Focus Reader** announces focused buttons and controls aloud using the Web Speech API.
- **🗺️ Interactive 2D SVG Campus Map:**
  - Floor switcher (`Outdoor`, `Ground`, `Floor 1`, `Floor 2`) and zoom controls.
  - Live pulsing user marker that smoothly animates along the planned route with real-time remaining distance and turn-by-turn cues.
- **⚠️ Live Broken Lift & Hazard Rerouting:**
  - Users can report a broken lift (e.g., *Block 34 Lift B*) or blocked ramp. The app immediately raises a high-visibility alert and recalculates a step-free detour via backup lifts and ramps.
- **📍 Nearby Daily Essentials Finder:**
  - One-tap access to the nearest accessible **Food Court**, **Tuck Shop**, **Washroom**, **Water & Rest Station**, **Academic Buildings**, and **Medical Aid**.
- **📷 Main Gate QR & Google Maps Integration:**
  - Includes a Main Gate tactile QR sticker preview, embedded physical LPU campus map, one-click external Google Maps walking directions, and a 3-step Judges Live Demo flow.

---

## 📁 Project Structure

```text
accessible-campus-navigator/
├── index.html   # Semantic, ARIA-labeled HTML structure and interactive SVG map
├── style.css    # WCAG AAA high-contrast theme, focus rings, and SVG animations
├── script.js    # Campus graph data, Dijkstra routing, speech synthesis/recognition, and UI logic
└── README.md    # Project documentation
```

---

## 🚀 Getting Started

1. **Keep all files together:** Ensure `index.html`, `style.css`, and `script.js` are saved in the same folder.
2. **Run the app:**
   - **Option A (Quick):** Double-click `index.html` to open it directly in any modern browser (Chrome, Edge, Safari, Firefox).
   - **Option B (Recommended for Voice Mic):** Serve via a local development server (such as VS Code **Live Server** or `npx serve`) so browser microphone permissions (`SpeechRecognition`) work smoothly.

> **Note:** An active internet connection is recommended on first load to fetch **Tailwind CSS** (via CDN), **Google Fonts (Inter)**, and the embedded **Google Map** iframe.

---

## 🗣️ Supported Voice Commands

| Language | Example Command | Action |
| :--- | :--- | :--- |
| **English** | `"From Main Gate to Block 38"` | Sets start & destination and previews route on map |
| **English** | `"Start route"` / `"Next step"` | Begins live guided navigation or advances step |
| **English** | `"Describe map"` / `"Distance left"` | Reads aloud current location, path, or remaining meters |
| **Hindi** | `"Block 34 se Food Court jana hai"` | Finds the nearest accessible Food Court from Block 34 |
| **Hindi / Punjabi** | `"Lift kharab hai"` / `"ਲਿਫਟ ਖਰਾਬ"` | Marks Lift B out of service and reroutes safely |

---

## 🛠️ Tech Stack

- **HTML5 & Semantic ARIA:** Screen-reader live regions (`aria-live`), radio groups, and accessible modal dialogs.
- **CSS3 & Tailwind CSS (CDN):** High-contrast dark UI (`#000000` base with `#FACC15` yellow, `#4ADE80` green, and `#38BDF8` sky-blue accents) with `48px+` touch targets.
- **Vanilla JavaScript (ES6+):** Custom undirected weighted graph, Dijkstra pathfinding algorithm, Web Speech API (`SpeechSynthesis` & `SpeechRecognition`), and `requestAnimationFrame` map marker interpolation.
