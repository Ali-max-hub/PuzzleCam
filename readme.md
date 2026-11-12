# PuzzleCam — Gesture Capture

A browser-based gesture-controlled photo booth application. No installation required, no backend, and zero dependencies to install.

---

## **DESCRIPTION**

PuzzleCam captures a photo using your hands as a "frame," turns it into a 3x3 black-and-white photo-effect puzzle, and lets you solve it using pinch gestures. Once completed, it is saved into a downloadable photo strip.

---

## **SYSTEM REQUIREMENTS**

- **Browser:** Chrome or Edge (recommended), Firefox
- **Hardware:** Webcam
- **Internet Connection:** Required to load the MediaPipe model (~10MB, first time only)
- **Local Server:** Required to run the app (cannot be opened directly as a local file)

---

## **INSTALLATION & SETUP**

### 1. Clone the repository

```bash
git clone https://github.com/Ali-max-hub/Puzzle.git
cd Puzzle
```

### 2. Launch a local server

The app uses ES modules and requires camera access, so it needs to run over HTTP.

Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension in VS Code and click **Go Live**.

### 3. Open in your browser

```
http://localhost:5500
```

Allow camera access when prompted by your browser.

---

## **PROJECT STRUCTURE**

```
Puzzle/
├── index.html       # App entry point
├── app.js           # Full logic (tracking, puzzle, gallery)
├── css/
│   └── styles.css   # Styles and layout
└── .gitignore
```

---

## **CONTROL GESTURES**

| Gesture | Action |
|---|---|
| Both hands making a pinch | Freeze the area and start the countdown |
| One hand making a pinch over a piece | Drag the puzzle piece |
| Closed fist (hold) | Save completed puzzle / Reset board |

---

## **APPLICATION LOGIC**

1. Show both hands to the camera and pinch to define the capture frame.
2. Hold the pinch during the countdown — the photo is taken automatically.
3. The photo is split into a 3x3 puzzle with a black-and-white photo booth filter.
4. Rearrange the pieces using pinch gestures.
5. Once completed, close your fist to save it to the strip with a fragmentation animation.
6. Download the complete strip once you have saved 3 puzzles.

---

## **TECH STACK**

- **[MediaPipe Tasks Vision](https://developers.google.com/mediapipe)** `v0.10.14` — Hand landmark detection
- **Canvas 2D API** — Rendering, puzzle pieces, photo booth effect
- **JavaScript (ES Modules)** — No frameworks
- **CSS Custom Properties** — Theming and layout

All external dependencies are loaded via CDN. No extra installation required.

---

## **TROUBLESHOOTING GUIDE**

### **The camera won't turn on**

Verify that no other application (Teams, Zoom, Discord, etc.) is using the camera in the background.

### **The app fails to load the model**

Check your internet connection. The MediaPipe model (~10MB) downloads from `storage.googleapis.com` and the runtime from `cdn.jsdelivr.net`. If either domain is blocked on your network, the app won't start.

### **The app shows a black screen**

Make sure you are opening the app via a local server (HTTP), not directly as a file from your file explorer.

### **Pinch gestures are not detected**

Ensure you have good lighting and that both hands are visible to your camera. Bring your index finger and thumb closer together until the yellow dot on the screen activates.

---

## **BROWSER COMPATIBILITY**

| Browser | Support |
|---|---|
| Chrome / Edge | Recommended |
| Firefox | Compatible |
| Safari | Limited (may require additional permissions) |
| Mobile | Limited (desktop recommended) |

---

## **LICENSE**

MIT — free to use, modify, and share.