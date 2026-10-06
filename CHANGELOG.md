# Changelog

All notable changes to KinoFlux Editor. The format follows [Keep a Changelog](https://keepachangelog.com/) and versions follow [Semantic Versioning](https://semver.org/).

Downloads for every version are on the [releases page](https://github.com/ntxmproducts/kinoflux-editor/releases).

## [0.1.2] - 2026-10-03

First release of the native (Rust + GPUI) KinoFlux Editor. It replaces the earlier Tauri-based desktop app and keeps its name, publisher and version line.

Downloads: [Windows installer](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-Setup-0.1.2-x64.exe) | [macOS disk image](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-0.1.2-macos-arm64.dmg) | [release page](https://github.com/ntxmproducts/kinoflux-editor/releases/tag/v0.1.2)

### macOS (Apple Silicon), verified on macOS 26.6
- Native macOS app: menu bar (About, Hide, Quit, File, Edit, Window, Help), Cmd shortcuts and hints, Finder / Dock / Open With file opening through the single running window, document types, high-resolution support and a proper icon.
- Helper programs bundled inside the app: FFmpeg, ImageMagick (with HEIC, AVIF, WebP and JPEG 2000), qpdf, Poppler and LibreOffice 26.2.6 (the official build, unmodified), so the Documents tools work without installing anything. The disk image is about 344 MB (360,250,711 bytes). It was re-published on 2026-10-04 with LibreOffice included, and both downloads were re-uploaded on 2026-10-05.
- Disk image is ad-hoc signed with the hardened runtime, shows the licence and has a branded background. It is **not notarized**, so the first start needs the one-time Gatekeeper step described in the [README](README.md#install).
- All 53 tools and 173 end-to-end cases passed on a Mac.

### Added
- **53 tools in five areas**, all running offline on your computer:
  - Video (15): convert / compress, compress to a target size, change format, change resolution, trim (thumbnail preview and range slider), change speed, remove audio, join, HLS stream package, extract audio, make a GIF, replace / mix audio, rotate / flip, burn in subtitles, save a frame.
  - Audio (6): convert, trim, volume / normalize, change speed, join, fade in / out.
  - Image (7): convert / compress, compress, resize, resize to a preset, crop / rotate, watermark, remove metadata.
  - PDF (12): merge, extract / remove / split pages, pages to pictures, extract text, rotate, compress, optimize, watermark, add a password, remove the password, remove document info, pictures to PDF.
  - Documents (13): Word, Excel and PowerPoint to PDF, PDF to Word / PowerPoint / Excel, update old Office files, Office to OpenDocument and back, spreadsheet to CSV and back, document to HTML and back.
- One window: file list (drag and drop, multi-select, reorder, Delete), tool panel with plain-language options, command palette (Ctrl/Cmd+K), presets per tool, results history (last 200 jobs), progress per file and overall, cancel, light / dark / system theme, remembers window size, panel width and last options.
- Draggable splitter between the file list and the tool panel (double-click resets). Narrow windows switch to a stacked layout. Footer buttons are icons with tooltips.
- Plain-language error messages (wrong password, damaged file, disk full, permission denied and more).
- **About window** (F1 or the info button): version, links, helper-program check, and in-app pages for Help, Privacy Policy, Terms, Licence, Third-party notices and Data handling.
- **Offline and private by design**: no network code, no telemetry, no account, no update check.
- Local rotated log file and crash reports in a per-user folder, a single running instance (files opened a second time go to the first window) and a first-run welcome card.
- Windows installer: per user or all users, Start menu entry, optional desktop icon, optional right-click "Open with KinoFlux Editor" entries, optional removal of your settings and logs on uninstall, silent install (`/VERYSILENT`), licence and privacy pages, high-DPI branded wizard.

### Notes
- The Windows installer and executable are not code-signed yet, so SmartScreen may show a warning.
- Bundled programs: FFmpeg 8.0 (GPL v3 build), ImageMagick 7.1.2-11, qpdf 12.2.0, Poppler 26.09.0, LibreOffice Portable 26.2.1.2 (Windows), LibreOffice 26.2.6 (macOS). Licences and the source-code offer are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
- There is only one edition: the full one, with LibreOffice included on Windows and macOS. The earlier "lite" package no longer exists.
- Known issue: the trim range slider. Type the times into the Start and End boxes. See [Known limitations](README.md#known-limitations).

## Earlier versions

Releases up to v0.1.1 were the previous Tauri-based Windows app. They remain available on the [releases page](https://github.com/ntxmproducts/kinoflux-editor/releases).
