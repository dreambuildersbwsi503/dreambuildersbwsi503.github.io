# [Click here for the MelodyMotion website.](https://dreambuildersbwsi503.github.io)

# Melody Motion

A web-based music accessibility tool built for the BWSI Create Challenge. It lets people who struggle with hand dexterity participate in music by using typing, touchpad gestures, or motion controls to play notes.

---

## Languages and Technologies Used

**HTML** - all three pages are plain HTML files. No build step needed.

**CSS** - styling is written directly inside each HTML file in `<style>` tags. No external CSS framework is used.

**JavaScript** - also written directly inside each HTML file in `<script>` tags. No libraries or package manager needed.

**Web Audio API** - this is a built-in browser API (no install required) that generates sound. It handles creating oscillators, controlling pitch, and shaping how notes attack and decay.

**Google Fonts** - the fonts Orbitron and Share Tech Mono are loaded from Google Fonts via a `<link>` tag. This requires an internet connection.

No frameworks like React, Vue, or Angular are used. No Node.js, no npm, no build tools. Every file runs directly in the browser.

---

## File Structure

```
melody-motion/
    index.html        main landing page
    touchpad.html     touchpad subpage
    keyboard.html     keyboard typing subpage
    README.md         this file
```

All three HTML files must stay in the same folder so the links between them work correctly.

---

## How to Run Locally

1. Download or clone this repository to your computer.
2. Open the folder on your computer.
3. Double-click `index.html` to open it in your browser.

That's it. There is no server to start, no install command to run, and no terminal needed. The files open directly in any modern browser (Chrome, Firefox, Safari, Edge).

If you want to use a local development server instead (for example if you run into browser security restrictions), you can use VS Code with the Live Server extension, or run this in your terminal from the project folder:

```
python -m http.server 8000
```

Then visit `http://localhost:8000` in your browser.

---

## How to Navigate the Website

**Main page (index.html)** - shows the Melody Motion landing page with three buttons:

- Play with Keys links to the keyboard page
- Motion Music links to the external gesture app
- Touchpad links to the touchpad page

**Keyboard page (keyboard.html)** - type solfege note names into the text box and press Play to hear them in sequence. Recognized notes are `do re mi fa sol la ti do2`. `do2` plays one octave higher than `do`. Use the controls at the bottom to set note duration, base note letter (A through G), and octave (1 through 6).

**Touchpad page (touchpad.html)** - eight circular buttons each play a solfege note. Press and hold a button to sustain the note. Tap and release quickly for a short note. Tap the same button multiple times quickly to get separate individual notes. Use the controls at the bottom to change the base note letter and octave.

---

## How Sound Works

When you press a button or click Play, the Web Audio API creates two oscillators (sine wave and triangle wave) and connects them to a gain node that controls volume over time. The pitch is calculated from a MIDI note number formula:

```
frequency = 440 * 2^((midi - 69) / 12)
```

The base note and octave selectors change the starting MIDI note. Each solfege step adds a fixed number of semitones on top of that.

---

## Deploying to GitHub Pages

1. Create a public repository on GitHub.
2. Upload `index.html`, `touchpad.html`, `keyboard.html`, and `README.md` to the root of the repository.
3. Go to Settings, then Pages, then set the source to Deploy from a branch, choose the main branch and the / (root) folder.
4. Save and wait about two minutes.
5. Your site will be live at `https://your-username.github.io/your-repo-name/`.

---

## Customization Notes

To change the button labels or descriptions on the main page, edit `index.html` and find the three `<a href=...>` blocks under the "Choose Your Experience" section.

To add your BWSI image, find the placeholder block in `index.html` that says `TODO: Replace this placeholder div` and swap it with an `<img>` tag pointing to your image file.

To add your description text, find the `<div class="description-placeholder">` block and replace the contents with your own paragraphs.
