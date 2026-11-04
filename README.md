# HUMAN.exe — G.A.R.Y.'s Enhanced Human Verification

**HUMAN.exe** is a deliberately ridiculous, webcam-controlled CAPTCHA parody. A familiar "I'm not a robot" checkbox turns into an over-serious biometric test administered by **G.A.R.Y.** (*General Authentication and Recognition Yardstick*). The humor is inspired by the escalating commands in Studio C's *Bop It* sketch; this is an original game, not a copy of the sketch or a real identity-checking service.

## Quick start (judges)

**Requirements:** A desktop or laptop with a webcam, a modern browser (Chrome or Edge recommended), Python installed, and an internet connection to load MediaPipe from jsDelivr.

1. Download the repository as a ZIP from GitHub (**Code → Download ZIP**) and extract it, or clone it with a Windows-compatible folder name:
   ```powershell
   git clone https://github.com/walker2023-glitch/G.A.R.Y..git GARY
   cd GARY
   ```
   **Windows note:** The repository name ends in a period; cloning without the final `GARY` folder argument may fail on Windows.
2. In the folder containing `index.html`, start a local server:
   ```powershell
   python -m http.server 8000
   ```
   If `python` is unavailable on Windows, try `py -m http.server 8000`.
3. Visit **http://localhost:8000** (not `file://`), click **I'm not a robot**, and wait for the CAPTCHA-style screen to transform.
4. Choose a browser voice if desired; click **BEGIN VERIFICATION** and allow webcam access.
5. Stand or sit far enough back that your face, shoulders, arms, and hands can be seen. Follow G.A.R.Y.'s spoken and on-screen commands. Use **RESTART** to play again.

**No account, API key, paid service, or build step is required.** Camera access works on localhost or HTTPS, not on arbitrary insecure web pages.

## What the game does

- Starts with a fake CAPTCHA, then switches to a green security-terminal interface.
- G.A.R.Y. introduces himself with **free browser speech synthesis**; available voices depend on your browser and operating system. Use the voice dropdown or sound toggle.
- MediaPipe Pose and Face Mesh process webcam landmarks in the browser. Visual dots indicate some tracked landmarks.
- Nine timed commands appear in this order:

| Command | What to do |
| --- | --- |
| **RAISE IT!** | Lift both hands above your head. |
| **TILT IT!** | Tilt your head sideways. |
| **WAVE IT!** | Move one hand side to side. |
| **FREEZE IT!** | Hold still. |
| **FLAP IT!** | Flap your arms like a chicken (two wingbeats). |
| **SALUTE IT!** | Bring a hand to your forehead. |
| **BOOGIE IT!** | Move or dance. |
| **BEG IT!** | Bring your hands together. |
| **DOUBT IT!** | Shake your head in disbelief. |

The first three challenges allow approximately **10 seconds each**, the next three **9 seconds**, and the remaining regular challenges **8 seconds**, starting after the spoken instruction. A recognized action must generally be held/confirmed for approximately one second. Movement-based actions may need repeated motion.

## Possible results and how to see them

| Outcome | How it happens | Expected on-screen result |
| --- | --- | --- |
| **Obedient robot (normal ending)** | Complete all nine regular challenges, and get a run without the bonus boss. | **HUMANITY DENIED**, **ACCESS DENIED**, and a joke about being too obedient. |
| **Independent human (secret ending)** | Stay clearly visible in the webcam and let **three consecutive regular challenges** time out without completing them. | **HUMAN VERIFIED**, **ACCESS GRANTED**, and "You have demonstrated independent thought and resistance to authority." |
| **LICK IT! boss (random ending)** | Complete the regular challenges; on approximately **50% of runs**, a final bonus challenge appears. | **LICK IT!** appears. **Do not lick the device.** After roughly five seconds the game confirms humanity for refusing. |

**Randomness:** The boss is selected once per new game, so you may need to restart several times to see it. The 50% chance is not a guarantee that every other run will include it.

**Important:** The program does not actually detect deliberate intent, tongue contact, or whether someone is a robot. The secret ending uses a playful timeout heuristic; missed gestures can also trigger it. The final boss never requires physical contact with a device.

## Troubleshooting

- **Camera does not start:** Allow camera permission; close apps using the webcam; run through `http://localhost:8000` or HTTPS.
- **Tracking does not recognize you:** Improve lighting, move back, and keep your head, shoulders, and arms in frame. Gesture detection is heuristic and may be imperfect.
- **No voice:** Unmute, choose another voice from the dropdown, and try Chrome or Edge. Available voices and playback behavior vary by OS/browser.
- **MediaPipe does not load:** Check internet access; this version fetches scripts/model assets from jsDelivr.
- **Port 8000 is busy:** Run `python -m http.server 8001` and visit `http://localhost:8001`.

## Buildathon information

- **Category/path:** Useless — the point is humor, absurdity, and an interactive experience, not real authentication.
- **Approved library:** MediaPipe Pose and Face Mesh, used for live webcam-based gesture tracking.
- **Other technology:** HTML, CSS, JavaScript, browser Web Speech API, and MediaPipe assets loaded from jsDelivr.
- **AI disclosure:** ChatGPT/Codex assisted with planning, implementation, and documentation. The submitter should review and test the final work.

## Privacy and limitations

Webcam analysis runs in the user's browser; the application does not intentionally upload or store webcam video. Third-party MediaPipe scripts and assets are downloaded from a CDN. This is a comedic prototype, **not a real CAPTCHA, lie detector, biometric identity system, or reliable assessment of human behavior**.

## For the Buildathon demo

Record a **5–10 minute video** that shows the CAPTCHA transformation, the voice and camera, several successful gestures, and at least one ending. Explain why the project fits the **Useless** category, how MediaPipe is used, what was challenging, and what you learned. Test the public repository and video links in an incognito window before submission.

**Testing status:** Source code is present, but hardware-dependent webcam/voice behavior must be tested on a real device before presenting it as fully verified.
