# 🐒 TypeMonkey — PDF Typing Practice App

A browser-based typing speed practice app that lets you upload your own PDF documents and type directly from their content. No backend, no server, no setup — just a single HTML file that works anywhere.
<img width="1897" height="886" alt="image" src="https://github.com/user-attachments/assets/32c8d029-21e9-41cb-b951-e754381c6b9d" />
<img width="1905" height="874" alt="image" src="https://github.com/user-attachments/assets/f9c7c0f1-4916-4216-8788-8557f725c58c" />
<img width="1905" height="874" alt="image" src="https://github.com/user-attachments/assets/28da9dda-46b1-4d9c-a63a-a1874df8c695" />

## ✨ Features

### 📄 PDF Mode
- Upload any PDF via click or drag-and-drop
- Visual page-by-page preview powered by PDF.js
- Navigate with Prev / Next buttons or **jump directly to any page** by typing the page number
- Extract text from any page and start typing instantly

### ✍️ Manual Text Mode
- Switch to manual mode and paste or type any custom text
- Great for practicing specific paragraphs or content outside a PDF

### ⌨️ Typing Experience
- **Colour-coded feedback** — grey (pending), green (correct), red (wrong), dim italic (auto-skipped)
- **Animated cursor** showing your exact position in the text
- **Auto-skip non-typeable characters** — em-dashes (—), curly quotes (""), copyright symbols (©), accented letters (é), and other symbols outside standard keyboard range are skipped automatically so you never get stuck
- **Progress bar** filling up as you advance through the text
- **No backspace** — corrections are not allowed, just like a real typing test
- **No pasting** — Ctrl+V, right-click paste, and drag-drop into the input are all blocked
- **No Ctrl+Z** — undo is blocked to prevent sneaky corrections

### 📊 Live Stats
Real-time stats update every 0.4 seconds while you type:

| Stat | Description |
|------|-------------|
| **WPM** | Words per minute |
| **Accuracy** | % of correctly typed characters |
| **Time** | Elapsed seconds since first keystroke |
| **Chars** | Total characters typed so far |

### ⏹ Finish & Save
- **Auto-completes** when you reach the end of the text
- **Manual stop** — click "Finish & Save" at any time to stop early and save a partial session record
- Partial sessions are clearly tagged in the dashboard history

### 📈 Dashboard
A full progress dashboard that persists across sessions:

- **6 summary cards** — Total Sessions, Best WPM, Avg WPM, Avg Accuracy, Total Practice Time, Total Chars Typed
- **WPM Trend Chart** — line chart plotting your WPM across all sessions to visualise improvement
- **Mistake Analysis** — two panels showing your most mistyped individual keys and hardest character pairs (bigrams), each with a frequency bar
- **Session History Table** — full log of every session with date, WPM, accuracy, duration, chars, and errors; partial sessions are clearly labelled

---

## 🚀 Getting Started

No installation needed.

1. Download `typing-monkey.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Upload a PDF or switch to Manual Text mode
4. Start typing!

> **Note:** Requires an internet connection on first load to fetch fonts (Google Fonts) and PDF.js from CDN. After that, PDFs are processed entirely in your browser.

---

## 💾 Data Storage

All progress is saved in your browser's **localStorage** — it persists through:
- ✅ Page refreshes
- ✅ Closing and reopening the browser
- ✅ Restarting your computer

Data is **local to your browser and device**. Opening the file on a different browser or computer starts fresh. Use the **🗑 Clear Data** button in the header to wipe all saved data.

---

## 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Structure |
| **CSS3** | Styling, animations, layout |
| **Vanilla JavaScript** | All app logic |
| **PDF.js** (v3.11.174) | PDF rendering and text extraction |
| **localStorage** | Persistent progress storage |
| **Google Fonts** | Space Mono + Playfair Display typography |

No frameworks. No build tools. No dependencies to install. Single file.

---

## 🔧 How the PDF Worker Fix Works

PDF.js requires a Web Worker to render PDFs off the main thread. When loaded from a CDN, browsers block the worker due to CORS/origin restrictions (especially when the file is opened via `file://`). TypeMonkey fixes this by:

1. Fetching the worker script as plain text
2. Wrapping it in a `Blob`
3. Passing a `blob://` URL to PDF.js — which is always same-origin

This eliminates the `Setting up fake worker` console warning and ensures PDF rendering runs on a real background thread.

---

## 📁 Project Structure

```
typing-monkey.html   ← The entire app (single file)
README.md            ← You are here
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a pull request.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

- [PDF.js](https://mozilla.github.io/pdf.js/) by Mozilla for PDF rendering
- [MonkeyType](https://monkeytype.com/) for inspiration on typing test UX

---

> Built as a personal productivity tool — because practicing typing with content you actually care about is way more effective than random word generators.
