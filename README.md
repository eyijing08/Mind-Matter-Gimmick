![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=threedotjs&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=for-the-badge&logo=google&logoColor=white)
![WebGL](https://img.shields.io/badge/WebGL-990000?style=for-the-badge&logo=webgl&logoColor=white)
![GLSL](https://img.shields.io/badge/GLSL-5586A4?style=for-the-badge&logo=opengl&logoColor=white)
![Hand Tracking](https://img.shields.io/badge/Hand_Tracking-0A84FF?style=for-the-badge)
![Particle System](https://img.shields.io/badge/Particle_System-8E01A7?style=for-the-badge)
![Interactive 3D](https://img.shields.io/badge/Interactive_3D-FF9F0A?style=for-the-badge)
![Vanilla JavaScript](https://img.shields.io/badge/Vanilla_JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Computer Vision](https://img.shields.io/badge/Computer_Vision-00B8D4?style=for-the-badge)
![Creative Coding](https://img.shields.io/badge/Creative_Coding-E91E63?style=for-the-badge)

# 🌌 Mind Matter Gimmick

An interactive, real-time 3D particle showcase controlled entirely through webcam hand gestures. Built with **Three.js**, **custom WebGL/GLSL shaders**, and **MediaPipe Hands**, this single-file web application morphs 50,000+ GPU-accelerated particles seamlessly between cosmic planets, a glowing neural brain core, 3D shapes, and custom uploaded logos.

> **[For MMU Mind Matter Gimmick Purpose Only]**

---

## ✨ Key Features

- **Dual Interactive Modes**: Smooth cinematic transition between **Interstellar Mode** (3D rotating planet with dual orbital rings) and **Neural Core Mode** (50,000 breathing brain particles with animated synaptic links and twinkling hub nodes).
- **Real-Time AI Hand Tracking**: Gesture recognition with hysteresis, smoothing buffers, and frame-miss tolerance for stable, responsive control—even on live stages.
- **Custom Image-to-Particle Morphing**: Upload custom images directly in the browser for the **MMU Logo**, **Mind Matters Logo**, and **Brain Core Shape**.
- **Decoupled Foreground & Background Brightness**: Independent horizontal sliders control the brightness of foreground logo particles while keeping the scattered nebula/starfield background locked and unaffected.
- **Live Color Customization & Presets**: Customize the Neural Core color and a 3-stop gradient for the neural network links, then save or load your entire setup (including resized images and slider levels) via `localStorage`.
- **Stage & Event Ready Controls**: Includes **Zen Mode** (hides all UI), **Auto Pilot Demo Mode**, **Freeze Tracking**, **Ultra/Fast Graphics Quality Toggle**, **Camera Switcher**, **PIP Preview Toggle**, and **Instant PNG Snapshots**.

---

## 🖐️ Hand Gesture Controls

### Interstellar Mode (Planet)
| Gesture | Action |
| :--- | :--- |
| 🖐 🖐 **Two Open Hands** | Move left/right to orbit; move hands apart/together to zoom in and out |
| ✊ ✊ **Two Closed Fists** *(Secret Trigger)* | Collapse the planet and unlock **Neural Core Mode** |

### Neural Core Mode (Brain)
| Gesture | Action |
| :--- | :--- |
| 🖐(heading down) 🖐(heading up) **Two Open Hands (Different Palm Orientation)** | Reveal **MMU Logo** *(requires uploaded image)* |
| 🖐 🤚 **Two Open Hands (Opposite Orientation)** | Reveal & lock **Mind Matters Logo** *(requires uploaded image)*. Once locked, move two open hands to rotate and tilt the logo in 3D |
| 🫰 **Finger Pinch / Heart** | Morph into a spinning 3D glowing **Heart** |
| ☝️ ✌️ 🤟 **1, 2, or 3 Fingers Raised** | Morph particles into 3D **Numbers (1–3)** |

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
| :---: | :--- |
| `E` | Reset to **Interstellar Mode (Planet)** |
| `R` | Reset to **Neural Core Mode (Brain)** & unlock frozen logo state |
| `F` | **Freeze / Resume** hand tracking |
| `H` | Toggle **Zen Mode** (hide/show all UI overlays and camera preview) |

---

## 🛠️ How It Works (Architecture)

This application runs as a self-contained web app with zero build steps, combining four core technologies:

1. **HTML & CSS (The Interface)**
   Handles the layout, translucent Apple-inspired dark glassmorphism panels, glowing action buttons, custom brightness sliders, and smooth CSS transitions for the auto-hiding sidebar and Zen Mode.
2. **MediaPipe Hands (The AI Vision)**
   Google's machine learning vision framework silently processes webcam frames in real time and outputs a 21-point 3D hand skeleton for up to two hands.
3. **Vanilla JavaScript (The Brain)**
   Acts as the central state controller. It translates MediaPipe's landmark coordinates into geometric distances, cross products, and smoothed gesture votes to distinguish poses (e.g., fists, pinches, palm orientation, and finger counts) while managing app transitions, presets, and UI controls.
4. **Three.js & GLSL Shaders (The 3D Engine)**
   Renders 50,000+ particles at high framerates by offloading morphing math to the GPU. JavaScript passes target position/color attributes (Brain, Numbers, Heart, Uploaded Logos) to custom vertex and fragment shaders, allowing the graphics card to interpolate positions, shimmer, and separate foreground/background brightness instantaneously.

---

## 🚀 Getting Started

Because modern browsers restrict webcam access (`getUserMedia`) on local `file://` URLs, serve the HTML file over **localhost** or **HTTPS**.

### Option 1: VS Code Live Server (Recommended)
1. Clone or download this repository.
2. Open the folder in **Visual Studio Code**.
3. Right-click the `.html` file and select **Open with Live Server**.
4. Allow webcam access when prompted.

### Option 2: Python Local Server
```bash
# Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

# Start a local HTTP server
python -m http.server 8000
```
Then open `http://localhost:8000` in your browser.

### Option 3: GitHub Pages
1. Push the repository to GitHub (rename your main file to `index.html`).
2. Go to **Settings → Pages** and deploy from your `main` branch.
3. Open your live `https://<your-username>.github.io/<your-repo-name>/` URL.

---

## 📸 Setup Tips for Live Demos

1. Hover near the **left edge of the screen** (or click the handle) to open the control panel, and click the **Pin icon** to keep it open while configuring.
2. Upload your **MMU Logo**, **Mind Matters Logo**, and optional **Brain Shape**.
3. Fine-tune the **MMU Logo Brightness** and **Mind Matter Brightness** sliders to match your projector or LED screen.
4. Click **💾 Save** so your configuration is stored locally in the browser for quick recovery via **📂 Load**.
5. Press **`H`** to enter **Zen Mode** for a clean, distraction-free full-screen presentation.

---

## 📄 Credits & License

- **Created by**: ENG YI JING
- **Copyright**: © 2026 MMU Mind Matter. All rights reserved.
