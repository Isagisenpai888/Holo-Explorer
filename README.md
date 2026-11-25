# Holo Explorer

Control a holographic reactor with your bare hands, using any webcam. Built with MediaPipe Hands and Three.js in a single HTML file. No build step.

## Run it

```bash
python -m http.server 8000
```

Open http://localhost:8000 in Chromium or Firefox and allow camera and microphone access. The first load needs internet for the CDN libraries.

### Using a phone as the camera (Linux)

```bash
sudo pacman -S scrcpy android-tools v4l2loopback-dkms
sudo modprobe v4l2loopback video_nr=10 card_label="Phone" exclusive_caps=1
scrcpy --video-source=camera --camera-facing=front --camera-size=1280x720 --camera-fps=60 --no-audio --no-playback --v4l2-sink=/dev/video10
```

Needs scrcpy 2.2+ and Android 12+. Press `C` in the app to switch cameras.

## Controls

| Gesture | Action |
|---|---|
| Pinch and hold | Spawn the reactor |
| Fist | Move it |
| Point and flick | Spin it |
| Two fists pulled apart, palms together then apart, or a counter-clockwise fist twist | Explode |
| Pinch a part, hold | Pull it out and show its info |
| Release a pulled part near your wrist | Wear it |
| Clap | Reassemble |
| Finger snap (mic) | Rings fit onto, or release from, your hands |

Keys: `E` explode, `S` or `W` rings on/off, `F` mirror, `B` black and white, `C` camera, `D` debug, `M` mute, `X` clear.

## Credits

Inspired by a hand-tracking holographic UI demo by @tonythetechie. Hand tracking by [MediaPipe](https://github.com/google-ai-edge/mediapipe), 3D by [Three.js](https://threejs.org).
