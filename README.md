# VR House Tour (Three.js)

## Introduction

This project is a **Three.js**-based VR house viewing application that supports:

* 360° panoramic room viewing
* Switching between rooms via clickable hotspots
* Smooth image transition animations
* Simulated network requests for loading VR scene data

The core data is stored in `data/vr.json`, simulating data retrieval from a server.

---

## Features

* **Three.js panoramic rendering**: Displays VR scenes using spherical or planar textures
* **OrbitControls camera control**: Supports panning, zooming, and rotating the camera
* **Smooth scene transitions**: Achieved using the `Track` timeline animation
* **Hotspot navigation**: Click on hotspot markers to navigate to the linked room
* **Dynamic hotspot positioning**: Real-time calculation of hotspot positions on screen, automatically hiding those behind the camera

---

## Project Structure

```
project/
│
├── index.html            # Project entry file (main logic)
├── data/
│   └── vr.json           # Simulated VR data (images, hotspots, etc.)
├── components/
│   ├── OrbitControls.js  # Custom camera controller
│   ├── VRFrame.js        # VR scene framebuffer rendering
│   ├── VRPlane.js        # VR plane/sphere mesh object
│   └── Track.js          # Animation timeline
└── assets/
    └── images/...        # Scene images
```

---

## Requirements

* Modern browser with **ES Module** support
* **WebGL** enabled (supported by most browsers)
* No build tool required — run directly in a local server environment

---

## Getting Started

npm i
npm start

---

## VR Data Format (`vr.json`)

```json
[
  {
    "id": 1,
    "imgSrc": "./assets/images/room1.jpg",
    "eye": [0, 0, 1],
    "marks": [
      {
        "name": "Living Room",
        "link": 2,
        "pos": [1, 0, 0]
      }
    ]
  }
]
```

**Field description**

* `id` — Unique scene ID
* `imgSrc` — Path to the panoramic image of the scene
* `eye` — Initial camera position
* `marks` — Hotspot list in the scene

  * `name` — Hotspot display name
  * `link` — Target scene ID
  * `pos` — Hotspot position in 3D space

---

## Interaction

* **Drag mouse** — Rotate camera view
* **Mouse wheel** — Zoom in/out
* **Click hotspot** — Jump to the linked room
* **Right-click disabled** — Prevents context menu interference

---

## Preview

(Add a screenshot or GIF here)

---

## License

MIT License

---
