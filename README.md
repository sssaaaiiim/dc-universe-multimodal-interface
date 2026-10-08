# DC Universe Multimodal Interface
 
An **adaptive multimodal interaction system** built as a single HTML page and themed around the DC Universe. It lets a person control the same interface in many different ways (mouse, touch, keyboard, voice, gestures, eye gaze and webcam hand movement) and automatically adjusts itself to the way they are using it.
 
The DC heroes (Batman, Superman, Wonder Woman, The Flash and Green Lantern) are the content layer: choosing a hero re-themes the whole screen with new colors, cursor, light beam, avatar and sound. The real purpose of the project is to show how one interface can serve many kinds of users and situations.
 
---
 
## What it is
 
A web-based demo of **adaptive modalities**: the interface does not assume one input method. It detects what you are using, reacts to it, and offers alternatives when one method is not suitable.
 
- **Say it:** "Superman" switches the hero theme.
- **Touch it:** swipe the hero cards or drag the emblem.
- **Look at it:** rest your gaze on a card for half a second to select it.
- **Wave at it:** swipe your hand in front of the webcam.
- **Type it:** use the command box when the microphone is not available.
---
 
## What you can do with it
 
### Control the interface
| Modality | How it works |
|---|---|
| Mouse | Hover and click hero cards and buttons |
| Touch | Tap and swipe; controls grow larger automatically |
| Keyboard | Left and right arrows change hero; Tab moves between controls |
| Voice | Say a hero name or command; the page replies by voice |
| Typed commands | Same commands as voice, entered in a text box |
| Drag gesture | Drag the emblem around the gesture stage |
| Swipe gesture | Swipe left or right across the hero cards |
| Hand gesture | Wave a hand in front of the webcam to go to the next or previous hero |
| Eye gaze | A gaze dot follows the pointer (or the webcam); 500 ms on a card counts as a fixation and selects it |
| Dwell-click | Hover on a button for 0.9 s and it clicks itself |
 
### Voice commands
- **Heroes:** "Batman", "Superman", "Wonder Woman", "Flash", "Green Lantern"
- **Navigation:** "next", "previous"
- **Emblem:** "red", "blue", "green", "bigger", "smaller", "reset"
- **System:** "run tests", "compact", "standard", "read profile"
- **Accessibility:** "high contrast", "calm", "zoom in", "zoom out"
- **Modes:** "gaze on", "gaze off", "stop listening"
### Adapt the interface to the person
- **Pointer precision:** shows *Fine* (mouse) or *Coarse* (touch) and resizes buttons to match.
- **Active modality:** displays the input method currently in use.
- **Text size (A+ / A-):** makes everything larger or smaller.
- **High contrast:** stronger white-on-black colors.
- **Calm mode:** turns off animations; switches on automatically if the device asks for reduced motion.
- **Narration:** reads hero profiles aloud.
- **Wake phrase:** commands only work after "Hey Justice League", which prevents accidental triggers.
- **Sound effects:** a short synthesized sound for each hero, with a mute option.
- **Saved preferences:** the page remembers your settings and last hero.
- **HUD density:** compact or standard layout.
### Measure how people interact
- **Modality Usage Report:** a live bar chart showing how often each input type was used.
- **Gaze panel:** shows gaze position, current target, dwell time and fixation counts per hero.
- **Diagnostic matrix:** 50 simulated test scenarios with a progress bar and a live console log.
---
 
## Where it is useful
 
- **Accessibility:** gives people with limited hand movement, low vision or speech needs more than one way to operate the same screen (voice, gaze, dwell-click, large text, high contrast).
- **Hands-free situations:** useful when hands are busy or dirty, such as cooking, repairs or lab work.
- **Kiosks and public displays:** works for touch, voice and gesture, so users choose what feels comfortable.
- **Human-computer interaction (HCI) teaching and research:** a small, readable example of multimodal input, eye-tracking fixation logic and adaptive UI, with a usage report for observing user behavior.
- **Gaming and entertainment interfaces:** themed controls, voice commands and gestures make menus feel more immersive.
- **Prototyping:** a base to test new input methods, thresholds (such as fixation time) and adaptive rules quickly.
---
 
## How to run
 
1. Save the file as `index.html`.
2. Open it in **Google Chrome or Microsoft Edge**.
3. Allow microphone and camera access when asked (only needed for voice, hand swipe and webcam gaze).
No installation, build step or server is required. For best results with camera and microphone, serve it over HTTPS (for example with GitHub Pages) or open it locally.
 
---
 
## How it works
 
- **Voice:** uses the browser's speech recognition. One command handler processes both spoken and typed text.
- **Gestures:** pointer events handle mouse and touch with the same code. A swipe is a mostly horizontal movement longer than 70 px.
- **Eye gaze:** the element under the gaze point is found on every move. Staying on the same card for 500 ms triggers a fixation.
- **Hand swipe:** webcam frames are compared to find where movement happens; a large sideways shift triggers a swipe.
- **Adaptation:** input events update the active-modality and pointer-precision cards and resize controls for touch.
- **Sound:** short oscillator patterns generated in the browser, with no audio files.
- **Storage:** preferences are saved in the browser's local storage.
---
 
## Limitations
 
- Voice recognition works best in Chrome or Edge and needs microphone permission and an internet connection.
- Eye gaze is a simulation using the mouse unless webcam gaze is enabled; webcam gaze is approximate and needs calibration by clicking.
- Hand swipe detects movement, not hand shape, so heavy background motion can cause false swipes.
- Embedded preview windows may block the camera and microphone.
- Not every control has been fully tested on all devices, so check the webcam features and wake phrase on your own device.
---
 
## Ideas for future work
 
- More heroes (Aquaman, Cyborg, Martian Manhunter) with their own themes
- Hand-shape gestures such as pinch and open palm
- CSV export of the usage report
- Automatic suggestions, for example offering voice control after repeated touch errors
---
 
*DC characters and names belong to their respective owners. This project is for educational use.*
