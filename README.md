# 🌸 Shirube V3

**The Ultimate Offline Japanese Immersion & Mining Environment**

Shirube is a standalone, hybrid desktop application designed to bridge the gap between reading native Japanese media and actively retaining vocabulary through Spaced Repetition (SRS). Read your books, watch your shows, mine your words, and track your mastery—all in one highly integrated workspace.

---

## ✨ Features

* **Zero-Config Portability:** Shirube runs entirely offline. The massive 2.3GB Japanese dictionary is heavily compressed and embedded directly into the app, meaning there are no messy setup wizards or databases to configure.
* **The Command Center:** A completely overhauled analytics dashboard featuring a GitHub-style daily immersion heatmap, JLPT progression charts (N5-N1), and real-time Jōyō/Kyōiku Kanji mastery tracking.
* **Smart Script Importer:** Drag and drop game scripts, TXT files, EPUBs, or subtitle files (SRT/ASS). The smart regex engine automatically detects dialogue formatting, merges multi-line text, ignores stage directions, and cleans it up into beautiful study cards.
* **Spotlight SRS:** Instantly harvest words and add them to your SRS deck directly from the global Spotlight Search (`Cmd+K` / `Ctrl+K`) no matter where you are in the app.
* **The Hybrid Server:** Open the "Network Access Link" from your library on your iPad or phone to read and mine from the couch while your PC silently handles the heavy database lifting.

## 🤝 Community & Integrations

* **Discord Rich Presence:** Show off your immersion grind! Shirube natively hooks into your local Discord client to broadcast the media you are studying, your live elapsed time, and your daily mined cards.
* **Discord Gengo Export:** Click the chat icon (💬) on any dialogue or vocabulary card to instantly copy a perfectly formatted Markdown snippet (with context sentences and translations) straight to your favorite Discord `#mining-finds` channel.
* **High-Fidelity Audio (VOICEVOX):** Ditch the robotic browser voices. Shirube natively bridges with the free [VOICEVOX](https://voicevox.hiroshiba.jp/) engine to provide studio-quality Japanese voice actors.
* **Auto-Sync to Anki:** Prefer Anki over Shirube's built-in SRS? Enable the AnkiConnect integration in Settings, and Shirube will silently build your Anki deck in the background as you mine.

---

## 🚀 Installation

Shirube is a 100% standalone, portable application. Your database is strictly yours and is stored safely in your local user folder. 

### 🍏 macOS (Apple Silicon & Intel)
1. Download and extract the `Shirube-macOS.zip` file from the latest Release.
2. Drag `Shirube.app` into your **Applications** folder.
3. **Security Bypass:** Because Shirube is an independent indie app, macOS Gatekeeper might block it the first time. To open it, **Right-Click (or Control-Click)** the app and select **Open**. Click "Open" again on the warning prompt.
*(Note: On the very first launch, the app may take a few seconds to extract its internal dictionary. Subsequent boots will be instant).*

### 🪟 Windows (x64)
1. Download the `Shirube.exe` file from the latest Release.
2. Move it to a folder of your choice (e.g., your Desktop or a dedicated Shirube folder).
3. **Security Bypass:** Windows Defender SmartScreen may display a blue "Windows protected your PC" warning. Click **More info**, then click **Run anyway**.

---

## 💾 Data & Backups

Your dictionaries, media, and SRS progress are securely saved in your system's `AppData` (Windows) or `Application Support` (Mac) folder as raw SQLite databases. 

* **To update the app:** Simply delete the old `.exe` or `.app` and replace it with the new one. Your data is stored externally and will load instantly.
* **To backup:** Open Shirube -> Settings -> Data Management, and click **Export Complete Backup**.
