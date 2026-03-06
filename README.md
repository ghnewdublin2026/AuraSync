# 🌌 AuraSync: The Bio-Acoustic Engine
> **Next-generation adaptive white noise. Synchronized to your biology. Mapped to your space.**

AuraSync is a mobile-first web application that moves beyond static sound loops. It uses the **Web Audio API** to synthesize real-time white noise and modulates it based on your heart rate and a 360-degree spatial orbit.



---

## 🚀 Quick Start (User Instructions)

### 1. Requirements
* **Browser:** Chrome or Safari (Mobile/Desktop).
* **Hardware:** Headphones are **required** for the Spatial 3D effect.
* **Environment:** A well-lit room is required for the Bio-Sync camera detection.
* **Protocol:** Must be served over **HTTPS** to allow Camera/Audio access.

### 2. Initialization
1. Open the app and tap **"INITIALIZE ENGINE"**. 
   * *Note: Browsers block audio until you interact with the page.*
2. You will hear a steady stream of white noise.

### 3. Using Bio-Sync (Heart Rate Detection)
1. Tap **"ACTIVATE BIO-SYNC"** and allow camera permissions.
2. **The Finger Technique:** Place your index finger lightly over the **front-facing camera** lens.
3. Keep your finger still. The app will analyze the microscopic color changes in your skin (PPG).
4. Once a pulse is detected, the **"Breathing Speed"** slider will lock and automatically sync to a calming ratio (approx. 1 breath per 2.5 heartbeats).

### 4. Exploring Spatial 3D
1. Wear your headphones.
2. Adjust the **"Spatial 3D Orbit"** slider.
3. At higher frequencies (e.g., 0.8 Hz), you will hear the noise "spin" rapidly around your head.
4. At lower frequencies (e.g., 0.1 Hz), the sound will slowly drift from left to right to behind you, reducing "static fatigue."

---

## 🛠️ Technical Implementation

### **The Audio Pipeline**
AuraSync generates noise mathematically rather than playing a file. This allows for infinite variation and zero data usage.
* **Synthesis:** `AudioBuffer` filled with random floats ($[-1.0, 1.0]$).
* **Modulation:** A `GainNode` acting as an LFO (Low-Frequency Oscillator) to simulate breathing.
* **Spatialization:** `PannerNode` set to `panningModel: 'HRTF'` (Head-Related Transfer Function) for true 3D positioning.

### **The Bio-Sync Algorithm**
The app uses **Photoplethysmography (PPG)**:
1. Captures a 10x10 pixel sample of the camera feed.
2. Extracts the **Red Channel** intensity.
3. Uses a **Local Maxima** peak-detection algorithm to identify heartbeats.
4. Smooths the data via a **Low-Pass Filter** to prevent erratic audio jumps.



---

## 📦 Deployment

AuraSync is a zero-dependency vanilla JS project. To deploy:
1. Upload `index.html` to any host (GitHub Pages, Vercel, Netlify).
2. Ensure **SSL/HTTPS** is enabled.
3. Open on an iPhone or Android device.

---

## 🛡️ Privacy Note
AuraSync processes all biometric data **locally** in your browser. Camera frames are analyzed in real-time and are never recorded, stored, or transmitted to any server.
