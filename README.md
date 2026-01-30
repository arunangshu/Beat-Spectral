# 🎵 Beat Spectral

A browser-based beat detector and audio visualizer with disco-style visual effects. Upload a song or capture system audio to see beats flash across your screen!

![Beat Spectral](https://img.shields.io/badge/Beat-Spectral-ff4757?style=for-the-badge)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## ✨ Features

- **🎧 Audio File Upload** - Load any audio file (MP3, WAV, OGG, etc.)
- **🎤 System Audio Capture** - Capture and visualize any audio playing on your system (Spotify, YouTube, etc.)
- **🌈 Disco Beat Flash** - Random colorful glow effects on each detected beat
- **📊 Real-time Frequency Visualizer** - See the audio spectrum in real-time
- **⚡ Adjustable Sensitivity** - Fine-tune beat detection with a percentage-based threshold
- **🎛️ Futuristic Player Controls** - Play/pause and seek through uploaded tracks

## 🚀 Getting Started

### Option 1: Upload a Song
1. Open `index.html` in your browser
2. Click **"📂 Upload Song"**
3. Select an audio file
4. Watch the beats flash!

### Option 2: Capture System Audio (Stereo Mix)
This lets you visualize beats from **any** audio source (YouTube, Spotify, games, etc.)

#### Windows Setup:
1. Right-click the speaker icon in your taskbar → **Sounds**
2. Go to the **Recording** tab
3. Right-click empty space → **Show Disabled Devices**
4. Right-click **"Stereo Mix"** → **Enable**
5. Open Beat Spectral and click **"🎤 Capture System Audio"**
6. When prompted, select **Stereo Mix** as the input device

#### Mac Setup:
- Install [BlackHole](https://existential.audio/blackhole/) virtual audio driver
- Set it as your system output, then select it in the browser

#### Linux Setup:
- Use PulseAudio loopback module: `pactl load-module module-loopback`

## 🎛️ Beat Detection Algorithm

The beat detection uses a **bin-by-bin percentage change** algorithm:

1. Analyzes the first 4000 frequency bins of the audio spectrum
2. Compares each bin's value to the previous frame
3. Calculates the **percentage change** for each bin
4. If **≥35% of bins** have changed more than the sensitivity threshold, a beat is triggered
5. A random disco color flashes across the top half of the screen

### Sensitivity Control
- **0%** - Most sensitive (any change triggers a beat)
- **Higher %** - Less sensitive (requires larger changes per bin)

## 🛠️ Technical Details

- **Web Audio API** - For audio analysis and playback
- **Canvas API** - For real-time frequency visualization
- **getUserMedia API** - For system audio capture
- **FFT Size**: 8192 (provides 4096 frequency bins)
- **Animation**: 60fps via `requestAnimationFrame`

## 📁 Project Structure

```
Beat-Spectral/
├── index.html    # Main application (single file)
└── README.md     # This file
```

## 🎨 Color Palette

The disco flash randomly selects from these colors:
- Hot Pink • Cyan • Yellow • Magenta
- Spring Green • Orange • Purple • Sky Blue
- Red • Green

## ⚠️ Notes

- **CORS Restrictions**: Cannot load audio from external URLs directly (use file upload instead)
- **Stereo Mix**: Availability depends on your audio drivers
- **Browser Support**: Works best in Chrome, Edge, and Firefox

## 📄 License

MIT License - Feel free to use, modify, and share!

---

Made with 💚 and lots of 🎵
