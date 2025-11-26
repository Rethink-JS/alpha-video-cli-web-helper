
# alpha-video-cli-web-helper

[![License: MIT](https://img.shields.io/badge/License-MIT-FFD632.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/platform-browser-black)](https://rethink-js.github.io/alpha-video-cli-web-helper)
[![Companion CLI](https://img.shields.io/badge/companion-alpha--video--cli-blue)](https://github.com/Rethink-JS/alpha-video-cli)

A visual helper tool for **[alpha-video-cli](https://github.com/Rethink-JS/alpha-video-cli)**.

This web utility allows users to drag and drop a folder of PNG frames to automatically detect file patterns, calculate frame rates, preview the animation sequence, and generate the precise CLI command required for encoding.

### [Launch Web Helper](https://rethink-js.github.io/alpha-video-cli-web-helper)

---

# Table of Contents

- [1. Purpose](#1-purpose)
- [2. Key Features](#2-key-features)
- [3. Usage](#3-usage)
- [4. Privacy and Security](#4-privacy-and-security)
- [5. Browser Limitations (File Paths)](#5-browser-limitations-file-paths)
- [6. Requirements](#6-requirements)
- [7. License](#7-license)

---

## 1. Purpose

The `alpha-video-cli` tool requires specific flags for input paths, frame rate (FPS), and file patterns (e.g., `Sequence_%05d.png`). Writing these manually can be error-prone.

This web helper solves that by analyzing your local files client-side and constructing the exact command string for you.

---

## 2. Key Features

- **Drag & Drop Analysis:** Instantly reads a folder to find PNG sequences.
- **Pattern Detection:** Automatically determines the `printf` style pattern (e.g., `%05d`) and start/end frame numbers.
- **FPS Auto-Detection:** Infers the likely frame rate (30, 60, 50, 24) based on the total frame count.
- **Transparency Verification:** Automatically scans source frames to verify they contain an alpha channel, preventing accidental encoding of opaque videos.
- **Live Preview:** Plays the animation loop in a canvas to verify continuity before encoding.
- **Smart Defaults:** Pre-configures quality settings (WebM: 50, HEVC: 90) to match the CLI defaults.
- **One-Click Copy:** Generates a ready-to-run terminal command.

---

## 3. Usage

1. Open the tool: [https://rethink-js.github.io/alpha-video-cli-web-helper](https://rethink-js.github.io/alpha-video-cli-web-helper)
2. Drag and drop your folder containing the PNG sequence onto the drop zone.
3. Review the auto-detected settings (FPS, Pattern, Start/End).
4. (Optional) Adjust quality sliders or output paths in "Advanced Settings".
5. Click **Copy Command**.
6. Paste the command into your terminal to run the encoder.

---

## 4. Privacy and Security

This tool is designed with a strict **Client-Side Only** architecture.

- **No Uploads:** Your images and folders are processed strictly within your browser's memory using the File System API.
- **No External Calls:** No assets are sent to a cloud server or third-party service.
- **Local Execution:** All logic runs locally on your machine.

---

## 5. Browser Limitations (File Paths)

Due to modern browser security standards, web pages cannot read the full absolute path of files on your hard drive (e.g., `/Users/username/Desktop/project/frames`). They can only see the relative folder name (e.g., `frames`).

**How to handle this:**

1. The tool will auto-fill a relative path (e.g., `./frames`).
2. If you are running the terminal command from the parent directory of your frames, this works immediately.
3. If not, you must update the `--input` path in the terminal.

> **Tip:** In macOS Terminal, you can drag and drop a folder from Finder directly into the terminal window to paste its absolute path.

---

## 6. Requirements

- A modern web browser with JavaScript enabled (Chrome, Safari, Firefox, Edge).
- The `alpha-video-cli` tool installed on your machine to run the generated commands.

To install the CLI:

```bash
npm install -g @rethink-js/alpha-video-cli
````

-----

## 7\. License

MIT License

GitHub: [https://github.com/Rethink-JS/alpha-video-cli-web-helper](https://github.com/Rethink-JS/alpha-video-cli-web-helper)

-----

by [**Rethink JS**](https://github.com/Rethink-JS)