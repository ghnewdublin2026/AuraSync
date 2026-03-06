# 🌌 AuraSync
> **Real-time adaptive white noise driven by your biology.**

AuraSync is a mobile-first web application that transforms static noise into a living, breathing soundscape. Using the Web Audio API and photoplethysmography (PPG), AuraSync synchronizes audio modulation with your resting heart rate and maps sound to a 360-degree spatial field.



## ✨ Features

* **🫁 Bio-Sync (Respiratory Mapping):** Uses the device camera to detect blood volume pulse (BVP). It automatically calculates your BPM and adjusts the "Breathing" gain modulation to a calming 2:1 ratio.
* **🎧 Spatial 3D Orbit:** Utilizes HRTF (Head-Related Transfer Function) to move the noise source in a physical XYZ coordinate space around the listener's head.
* **🌊 Fractal Noise Generation:** Pure, browser-generated white/pink noise—no loops, no seams, zero bandwidth after initial load.
* **📱 Mobile Optimized:** Low-latency performance with touch-friendly controls and background audio support.

## 🛠️ Technical Stack

- **Engine:** Web Audio API
- **Spatiality:** `PannerNode` (HRTF Panning Model)
- **Vision:** `getUserMedia` + Canvas Pixel Analysis for PPG
- **Frontend:** Vanilla JS / CSS Custom Properties

## 🚀 Quick Start

1. Clone the repo.
2. Serve via HTTPS (Camera and AudioContext require a secure context).
3. Open on a mobile browser with headphones.
4. Press **Start** and place your finger over the rear camera for Bio-Sync.
