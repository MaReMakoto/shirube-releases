# 🌸 Shirube Roadmap

## 🟢 Current State: v3.1 (The Native Environment)
* **Status:** Deployed.
* **Core Loop:** Hybrid web/desktop architecture via Wails and Go.
* **Features:** SQLite media library, WanaKana typing, dynamic offline hover dictionary, Google auto-Kanji drawing pad, native OS hotkeys, Voicevox TTS engine, and Anki-Connect integration.
* **Under the Hood:** Custom de-inflector engine currently implemented for baseline grammar parsing.

* **Phase 1 Done**

---

## ~~🟡 Phase 1: Foundation & Independence~~
### ~~v3.1.5 - The Architecture Overhaul~~
* ~~**Modular Codebase:** Refactor the massive monolithic files (`main.js`, `main.go`) into clean, object-oriented, and modular components (e.g., `audio.js`, `srs.js`, `api.go`, `db.go`).~~
* ~~**Component Audit:** Establish a clean baseline for the current tokenizer, de-inflector, and dictionary databases before adding new intelligence features.~~

### ~~v3.2 - The Export Engine~~
* ~~**Native `.apkg` Generation:** Build a Go-based Anki package generator to create standalone `.apkg` files directly from the Vault. Removes the dependency on Anki-Connect for users who want to back up, share, or import decks into AnkiWeb/AnkiMobile.~~

### ~~v3.3 - Advanced SRS Mechanics~~
* ~~**Review Forecasting:** Introduce a "Next Review Due" UI component. Provide users with a visual timeline and specific counts for reviews due later today, tomorrow, and over the next week to help them pace their lessons.~~
* ~~**Dedicated Kanji SRS:** Expand from a vocabulary-first miner into a comprehensive character mastery tool. Build an independent Spaced Repetition queue exclusively for Kanji, tracking Onyomi, Kunyomi, and meanings separately from standard dialogue cards.~~


---

## 🟠 Phase 2: Active Immersion (The "Cinema" Update)
### v4.0 - Integrated Media Player & Reading Room
* **Cinema Room:** A native local video player utilizing the HTML5 `<video>` tag. Users drag an MP4/MKV and a subtitle file into Shirube.
* **Interactive Subs:** Render an interactive subtitle overlay. Clicking a word auto-pauses the video and triggers the dictionary hover card.
* **Zero-Setup Native Reader:** Upgrade the EPUB/TXT parser into a dedicated "Reading Mode" that also accepts text-based `.pdf` files. Read native text directly in the app and click any word to harvest it without leaving the flow of the book.

### v4.1 - Granular Analytics
* **Per-Media Statistics:** Link harvested vocabulary directly to specific `mediaIds`. Clicking a game in the library will show exactly how many N5-N1 words were learned from that specific playthrough, unique Kanji encountered, and playtime-to-vocab ratios.

---

## 🔴 Phase 3: The Live Game Engine (GSM Inspired)
### v5.0 - Text Hooking Pipeline
* **Live Clipboard & WebSocket Listeners:** A background Go routine that listens to tools like Textractor. 
* **Real-Time Mining:** As the user plays a visual novel, the text streams instantly into Shirube's Study Room, automatically generating furigana, translations, and Voicevox audio on the fly.
* **Second Screen Companion:** Optional Hybrid Server iPad/Mobile companion view so a tablet can sit on the desk acting as the live dictionary, Kanji pad, and SRS voter while the main monitor stays clean for gameplay.

---

## 🟣 Phase 4: Hardware & Vision (Kamui Inspired)
### v6.0 - The OCR Ecosystem
* **Direct Capture Card Integration:** Tap directly into the OS hardware libraries (DirectShow/MediaFoundation) via Go to pull video feeds directly from a capture card, bypassing OBS entirely.
* **Local Video OCR:** Run a highly precise, lightweight local OCR engine over the capture card feed to pull Kanji straight off console gameplay (Switch/PS5) and pipe it directly into the hover dictionary.
* **Manga & Scanned PDF OCR:** An integrated image/PDF viewer that allows users to draw bounding boxes over manga speech bubbles. The local OCR engine instantly converts the image box into dictionary-ready text.

---

## 🌌 Phase 5: The Intelligence Makeover
### v7.0 - Context-Aware Parsing & AI
* **Dictionary Brain Transplant:** Upgrade the backend tokenizer to use Sudachi and the `mecab-ipadic-NEologd` dictionary to seamlessly handle modern anime slang, contractions, and VTuber names.
* **The Pre-Immersion Profiler (Prep Room):** Drop a game script into Shirube to cross-reference it against your Vocab Vault. Output a "Readability Score" and generate a "Prep Deck" of the 50 most frequent unknown words to learn *before* playing.
* **Offline Grammar Tutor (Local LLM):** Integrate a local, offline LLM (like `llama.cpp`). Users click "Explain Grammar" to break down exact nuances, slang, and particle usage—acting as an invisible normalizer between anime-speak and textbook Japanese.
* **Commute Mode (Audio Generation):** A one-click export that takes the SRS Review Queue and stitches it into a single `.mp3` file (Voicevox Japanese -> 3-second pause -> English meaning) for passive listening while driving or doing chores.
