# HUMAN.exe — The World's Least Reasonable CAPTCHA

A comedic, webcam-controlled CAPTCHA inspired by the escalating absurdity of Studio C's *Bop It* sketch. This is an original parody-style interactive experience, not a reproduction of the sketch.

## Buildathon path
**Useless** — an intentionally unnecessary and entertaining verification system.

## Approved tool
**MediaPipe** Pose and Face Mesh (via CDN), used meaningfully to detect human gestures in real time.

## Run
From this folder:

```bash
python -m http.server 8000
```

Open `http://localhost:8000` in a modern browser, allow camera access, and click **Begin Verification**. Internet access is required to load MediaPipe scripts and model files from jsDelivr. No API key is needed.

## Challenges
1. Raise both hands above your head.
2. Tilt your head.
3. Flap both arms twice.
4. Hold still.
5. Get rejected anyway.

The app draws tracked landmarks and uses text-to-speech for absurd instructions. All camera processing happens in-browser; the app does not upload video.

## Demo checklist
- Test webcam and all four gestures in your actual lighting/camera setup.
- Record a **5–10 minute demo** explaining the project, the Useless path, MediaPipe, and what you learned.
- Push source to a **public GitHub repository** with development history.
- Disclose AI assistance and MediaPipe CDN usage in your submission.
- Test public video and repository links in an incognito window.

## Known limitations
- Gesture thresholds are heuristic; camera position and lighting affect reliability.
- The chicken-flapping detector counts two up-to-down cycles; don't hold the arms up continuously.
- Speech synthesis voice depends on browser/OS.
- This is entertainment, not actual human authentication.
