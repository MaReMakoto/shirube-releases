# Shirube

Shirube is a standalone desktop application that combines reading native Japanese media with a Spaced Repetition System (SRS) for vocabulary retention. It functions as a centralized environment for media tracking, text parsing, offline dictionary lookups, and flashcard management.

---

<div align="center">
  <img src="https://github.com/user-attachments/assets/e8355f55-57f1-4f4f-9869-173076387a20" alt="Shirube Library View" width="850">
  <p><i>The main library interface for tracking Japanese media.</i></p>
</div>

<br>

## 📖 Core Functionality

Shirube is built to process raw Japanese text and convert it into actionable study material. 

<div align="center">
  <img src="https://github.com/user-attachments/assets/68ae031c-af9e-4da7-9807-cbee75465140" alt="Shirube Study Room and Hover Dictionary" width="850">
  <p><i>The Study Room parsing text with the integrated offline dictionary.</i></p>
</div>

<br>

### Media & Text Parsing
* **File Importer:** Import `.epub`, `.srt`, `.ass`, `.txt`, or `.csv` files. The regex engine formats the text into line-by-line dialogue cards, filtering out standard stage directions.
* **Furigana Generation:** Processes raw Japanese text to automatically generate Furigana using a localized NLP engine (Kagome).
* **Inline Editing:** Correct OCR scanning errors directly on the dialogue cards. Editing a card automatically regenerates the Furigana and translation.
* **Chapter Organization:** Group parsed scripts into custom tabs (e.g., by chapter or episode) to manage large files.
* **Offline Dictionary:** Hold `Shift` and hover over any Japanese word to view its reading and meaning. Features both English and Japanese-to-Japanese definitions.
* **Spotlight Search:** Press `Cmd+K` / `Ctrl+K` to open a global dictionary search overlay from any view in the application.

### Spaced Repetition System (SRS)
* **Vocab & Kanji Tracking:** Save words directly from the dictionary popup to your SRS deck. The system captures the dictionary form, reading, meaning, and the exact context sentence it was found in.
* **Review Algorithm:** Uses a scheduled 9-stage spacing algorithm (Levels 0-8, from Learning to Burned) to schedule reviews based on accuracy.
* **Auto-Kana Input:** During reviews, typed Romaji is automatically converted to Hiragana/Katakana.
* **Configurable Settings:** Adjust the daily limit for new vocabulary, change the SRS pacing multiplier (0.5x to 1.5x), and toggle between strict or flexible grading for Kanji readings.

### Learning Hub & Kanji Pad
* **Kanji Drawing Pad:** Draw unrecognized characters on the canvas. The application recognizes the strokes and provides the Onyomi, Kunyomi, meaning, and JLPT level.
* **Compendium:** Browse a master list of Kanji categorized by JLPT level, Japanese School Grade, or WaniKani level, and add them manually to your SRS queue.

<br>

## 📊 Analytics Dashboard

The Command Center provides visual analytics based on your reading and review history.

<div align="center">
  <img src="https://github.com/user-attachments/assets/f744eee4-cccb-443f-baa0-b9f8c626395c" alt="Shirube Analytics Dashboard" width="850">
  <p><i>The analytics dashboard tracking immersion metrics and JLPT progress.</i></p>
</div>

<br>

* **Activity Heatmap:** A daily tracker that logs the volume of dialogue lines parsed and vocabulary cards mined.
* **Review Forecast:** Displays the exact number of SRS reviews due currently, later today, tomorrow, and over the next 7 days.
* **JLPT Progression:** Cross-references your harvested vocabulary and Kanji against standard N5-N1 databases to chart your coverage of each level.
* **Overall Kanji Mastery:** Progress bars tracking your completion of the standard 1,026 Kyōiku (Elementary) and 2,136 Jōyō (Adult Literacy) Kanji lists.
* **Time Tracking:** A built-in stopwatch in the Study Room logs your active reading time, which is aggregated on the dashboard.

<br>

## ⚡ Architecture & Integrations

| Built-in Spaced Repetition | Discord Rich Presence |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/9ee47c29-7820-4a58-acd8-8173b5ccdd72" width="400" alt="SRS Flashcard"> | <img src="https://github.com/user-attachments/assets/9be604bf-86a7-4163-8a8d-088297067852" width="400" alt="Discord Status"> |
| *The native review interface testing meaning and context.* | *Discord RPC broadcasting current media and daily mined cards.* |

<br>

* **Local Network Server (Hybrid Mode):** The desktop application hosts a local web server. By navigating to the provided local IP address on a mobile device or tablet (secured via an auto-generated token), you can access the application interface from a mobile browser while the desktop handles the database processing.
* **Cover Art APIs:** Automatically fetches cover art for your library entries using the Twitch/IGDB API (Games), TMDb (TV), AniList (Anime/Manga), and iTunes (Podcasts/Audiobooks).
* **Discord Rich Presence:** Connects to your local Discord client to display the media you are currently reading, elapsed time, and daily mined card count.
* **Discord Markdown Export:** A dedicated button on dialogue and vocabulary cards copies a pre-formatted Markdown snippet to your clipboard for sharing in chat applications.
* **VOICEVOX TTS:** Integrates with the local [VOICEVOX](https://voicevox.hiroshiba.jp/) application to generate synthesized native Japanese audio for dialogue lines and vocabulary words.
* **Anki Integration:** * **Export:** Generate standard `.apkg` files from your SRS Vault to import into Anki.
  * **Live Sync:** Enable the AnkiConnect integration to automatically push newly mined cards to your desktop Anki application in the background.

<br>

<div align="center">
  <img src="YOUR_CROSS_PLATFORM_ECOSYSTEM_BANNER_LINK_HERE.png" alt="Shirube Cross-Platform Ecosystem: Monitor, iPad, and iPhone Views" width="950">
  <p><i>The UI adapts to desktop and mobile browser environments via the Hybrid Server.</i></p>
</div>

<br>

---

## 🚀 Installation

Shirube is a portable application. The required databases and dictionaries are embedded directly into the executable.

### 🍏 macOS (Apple Silicon & Intel)
1. Download and extract the `Shirube-macOS.zip` file from the latest Release.
2. Move `Shirube.app` into your **Applications** folder.
3. **Security Bypass:** As an unsigned application, macOS Gatekeeper may block the initial launch. To open it, **Right-Click (or Control-Click)** the application and select **Open**. Click "Open" again on the subsequent prompt.
*(Note: On the first launch, the application requires a few seconds to extract its internal dictionary. Subsequent launches will be instantaneous).*

### 🪟 Windows (x64)
1. Download the `Shirube.exe` file from the latest Release.
2. Move it to a directory of your choice.
3. **Security Bypass:** Windows Defender SmartScreen may flag the executable. Click **More info**, then select **Run anyway**.

---

## 💾 Data Management

User data (dictionaries, media library, settings, and SRS progress) is stored locally as SQLite databases in the following directories:
* **Windows:** `%APPDATA%\Shirube`
* **macOS:** `~/Library/Application Support/Shirube`

*(Note for returning users: If you are upgrading from V3 or earlier, Shirube will automatically and safely migrate your old `ImmersionTracker` folder on first boot!)*

**Updating:** To update the application, delete the old `.exe` or `.app` file and replace it with the new version. Your external database files will not be affected.

**Backups:** You can export your entire database as a `.json` backup file by navigating to **Settings -> Data Management -> Export JSON Backup**.
