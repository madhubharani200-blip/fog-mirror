# Fog Mirror

A webcam  mirror that fogs up when you breathe on it. Pinch to draw on the fog with your fingertip, make a fist and swipe to wipe a wide area clear.

**Live demo:** https://madhubharani200-blip.github.io/fog-mirror/

Everything runs in your browser. No video, audio, or data is uploaded or leaves your machine.

## Controls

| Action | How |
| --- | --- |
| Fog up | Breathe on the mic, or hold **Space** |
| Draw | Pinch thumb and index finger, move your fingertip |
| Wipe | Make a fist and swipe |
| Brush size | The **brush** slider, bottom left |
| Clear | **C** |
| Save PNG | **S** or the shutter button |
| Readouts | **D** |
| Back to start | **Esc** |

## How it works

- Three stacked canvas layers: mirrored camera, a hidden fog canvas, and a blurred and tinted frost layer masked by the fog with `destination-in`.
- Drawing and wiping subtract from the fog canvas with `destination-out`.
- Breath detection uses the mic with noise suppression turned off and a noise floor that adapts to the room.
- Pinch is measured relative to hand size, so it works near or far from the camera.
- Hand tracking and face detection use MediaPipe, running locally in the browser.

## Run locally

The camera only works on https or localhost, not by double-clicking the file.

```
python3 -m http.server
```

Then open `http://localhost:8000/index.html` in Chrome or Edge.

## Built with

HTML, CSS, vanilla JavaScript, [MediaPipe Hands](https://github.com/google/mediapipe) and Face Detection.

## Credits

Built by Mabhi. Inspired by [Fog Mirror by Lilian]
