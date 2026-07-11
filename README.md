# 🌀 Harmonic Spirograph 3D - Audio Reactive Visualization

A stunning, real-time 3D audio-reactive spirograph visualization built with **Three.js** and the **Web Audio API**. Watch harmonic curves dance, morph, and pulse in sync with your music.

![Harmonic Spirograph](https://img.shields.io/badge/Three.js-r160-000000?logo=three.js&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

---

## ✨ Features

### 🎨 Visual Effects
- **Dynamic 3D Spirograph** - 6000-point harmonic curve with real-time deformation
- **Shape Morphing** - 5 preset shapes that smoothly transition into each other
- **Audio Reactivity** - Geometry responds to bass, mid, treble, and volume
- **Bloom Glow** - Unreal Engine-style bloom post-processing
- **Motion Blur** - Afterimage effect for light trails
- **Trail System** - Multiple ghost copies with fading opacity
- **Color Cycling** - HSL rainbow gradient along the curve
- **Audio Spectrum** - Real-time frequency bar display at bottom

### 🎵 Audio Input
- **File Upload** - Load any audio file (MP3, WAV, OGG, etc.)
- **Microphone** - React to live audio input (voice, instruments, etc.)

### 🎮 Interactive Controls
| Control | Description |
|---------|-------------|
| **Curl Density** | Adjust the complexity of the spirograph pattern |
| **Evolution Speed** | Control how fast the shape evolves over time |
| **Audio Reactivity** | Sensitivity of the visualization to sound |
| **Bloom Intensity** | Strength of the glow effect |
| **Color Speed** | Rate of hue cycling through the spectrum |
| **Space Drift** | Movement amplitude through 3D space |
| **Pulse/Breath** | Rhythmic pulsation synced to audio |
| **Trail Effect** | Length of the motion trail |
| **Morph Speed** | How quickly shapes transition |
| **Motion Blur** | Intensity of the afterimage effect |

### 🎬 Recording
- **Video Capture** - Record your visualization with audio (WebM format, 60 FPS, 25 Mbps)
- **Composite Output** - Captures both 3D scene and audio spectrum

### 🖥️ UI/UX
- **HUD-Style Panel** - Cyberpunk-inspired control interface
- **Auto-Hide** - Controls fade after 3 seconds of inactivity
- **Toggle Visibility** - Show/hide the control panel
- **Responsive** - Adapts to any screen size
- **Scanline Effect** - Subtle retro CRT aesthetic

---

## 🚀 Quick Start

### Option 1: Open Directly
1. Download or clone this repository
2. Open `index.html` in a modern browser (Chrome, Firefox, Edge)
3. Load an audio file or enable microphone
4. Enjoy the show!

### Option 2: Local Server (Recommended)
Due to browser security policies for audio contexts, running via a local server is recommended:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (http-server)
npx http-server -p 8000

# Using PHP
php -S localhost:8000
```

Then navigate to `http://localhost:8000`

---

## 🛠️ Technical Details

### Dependencies (CDN)
- **Three.js** r160 - 3D rendering engine
- **EffectComposer** - Post-processing pipeline
- **UnrealBloomPass** - Bloom glow effect
- **AfterimagePass** - Motion blur/trail effect

### Browser Requirements
- WebGL 2.0 support
- Web Audio API
- MediaRecorder API (for video recording)
- ES6 Modules

**Recommended Browsers:**
- Chrome 90+
- Firefox 88+
- Edge 90+
- Safari 15+

---

## 📁 Project Structure

```
├── index.html          # Main application (single-file)
├── README.md           # This documentation
└── .gitignore          # Git ignore rules
```

---

## 🎛️ How to Use

### 1. Load Audio
- Click **📁 File** to upload an audio file from your device
- Click **🎤 Mic** to use your microphone as input

### 2. Adjust Visualization
Use the sliders in the HUD panel to customize:
- Shape complexity and evolution
- Color behavior
- Motion and drift
- Post-processing effects

### 3. Record Video
- Click the **⦿ Record** button (top-right) to start recording
- Click again to stop and download the `.webm` file
- Recording includes both video and audio

### 4. Toggle Spectrum
- Click **⊟** (top-right) to show/hide the audio spectrum display

### 5. Hide UI
- Click **⧉** or wait 3 seconds of inactivity to hide controls
- Move mouse or press any key to bring them back

---

## 🎨 Shape Presets

The visualization morphs between 5 mathematical curve types:

1. **Classic Spirograph** - Traditional harmonic pattern
2. **Toroid/Knot** - Donut-shaped interwoven curve
3. **Rose/Flower** - Petal-like radial symmetry
4. **Spiral Wave** - Helical wave pattern
5. **Intertwined Knot** - Complex multi-axis weaving

---

## 🔧 Customization

### Modify Parameters
Edit the `params` object in the JavaScript section:

```javascript
let params = {
    curls: 7,           // Default curl density
    evolve: 0.30,       // Default evolution speed
    reactivity: 1.0,    // Default audio sensitivity
    colorSpeed: 0.40,   // Default color cycling speed
    drift: 120,         // Default spatial drift
    pulse: 0.40,        // Default pulse intensity
    trail: 8            // Default trail length
};
```

### Add New Shapes
Add a new function to the `shapePresets` array:

```javascript
// 5 - Your custom shape
(t, f1, f2, f3, f4, phi) => ({
    x: /* your formula */,
    y: /* your formula */,
    z: /* your formula */
})
```

### Change Colors
Modify the HSL values in `updateCurve()`:

```javascript
c.setHSL(((hue + i/NUM_POINTS*0.5) % 1), 1.0, 0.55);
//                    ^ saturation  ^ lightness
```

---

## 📝 Notes

- **Audio Context Policy**: Browsers require user interaction before playing audio. Click anywhere on the page first.
- **Microphone Permissions**: You'll be prompted to grant microphone access when using live input.
- **Recording Format**: Videos are saved as `.webm` files. Convert to MP4 if needed using tools like FFmpeg or online converters.
- **Performance**: For best performance, close other GPU-intensive applications. Reduce point count (`NUM_POINTS`) if experiencing lag.

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| No audio visualization | Click anywhere on page to unlock audio context |
| Microphone not working | Grant permissions when prompted; check browser settings |
| Recording not capturing audio | Ensure audio source is connected before recording |
| Low FPS | Reduce `NUM_POINTS` or disable motion blur |
| Black screen | Check browser console for WebGL errors; update graphics drivers |

---

## 📄 License

MIT License - Feel free to use, modify, and distribute.

---

## 🙏 Acknowledgments

- **Three.js** team for the amazing 3D library
- **Web Audio API** contributors
- Inspired by classic spirograph toys and harmonic motion studies

---

## 📬 Contact

Enjoying the visualization? Consider starring the repository! ⭐

For issues or feature requests, please open a GitHub issue.

---

<p align="center">
  <em>Created with ❤️ and music</em>
</p>
