# HUMAN.exe — G.A.R.Y.'s Enhanced Human Verification

An original satirical browser game inspired by the escalating absurdity of Studio C's *Bop It* sketch. This is not a reproduction of the sketch or a real authentication service.

## Buildathon
- **Path:** Useless
- **Approved library:** MediaPipe Pose and Face Mesh (via jsDelivr CDN)
- **AI assistance:** ChatGPT/Codex used to help write and revise source code; all behavior should be reviewed and tested by the submitter.

## Run

```bash
python -m http.server 8000
```

Visit http://localhost:8000 in a modern desktop browser, click the parody CAPTCHA, then **BEGIN VERIFICATION**. Grant webcam permission. Internet access is needed for MediaPipe. HTTPS or localhost is required for webcam access.

## Features
- Ordinary CAPTCHA-style landing screen that transforms into a futuristic security system.
- G.A.R.Y. (General Authentication and Recognition Yardstick) introduces the experience.
- **Free, local browser speech synthesis**, with a voice selector using voices installed on the user's browser/operating system. No ElevenLabs or API keys.
- Webcam-detected commands: RAISE, TILT, WAVE, FREEZE, FLAP, SALUTE, BOOGIE, BEG, and DOUBT.
- 50% chance of a fictional **LICK IT!** final boss. **Never lick your device**; the challenge resolves without contact.
- Secret independent-thought ending after three consecutive timed-out challenges while the player remains visible.
- Standard comedic failure ending after completing all regular challenges.

## Privacy
Camera processing is local to the browser. The app does not upload or save webcam footage. MediaPipe scripts and model assets are fetched from jsDelivr.

## Known limitations
- Gestures use heuristics and are sensitive to lighting, framing, camera position, and browser performance.
- A missed gesture may be mistaken for refusal. The secret ending is deliberately comedic, not a scientifically reliable judgment of intent.
- Voice selection varies by operating system and browser. Some browsers may delay or block speech until a user interaction.
- The game is a parody, not an actual CAPTCHA or biometric identity verification system.

## Submission checklist
- Test all gestures and the voice in a real browser.
- Verify both possible finale paths over multiple runs.
- Record a 5–10 minute demo showing working functionality and explaining MediaPipe and the Useless path.
- Include a public GitHub repository with development history.
- Disclose major external resources and AI assistance.
- Test public links in an incognito window.