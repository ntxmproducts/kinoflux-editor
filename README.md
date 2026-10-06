<div align="center">

<img src="assets/logo.png" alt="KinoFlux Editor app icon: a blue to teal letter K made from a film strip with a play button" width="132" />

# KinoFlux Editor

### Native, fully offline video, audio, image, PDF and document tools

**53 tools in one small window.** No uploads, no account, no telemetry, no network code.<br/>
For Windows 10/11 and macOS (Apple Silicon).

<br/>

[![Version 0.1.2](https://img.shields.io/badge/version-0.1.2-0ea5e9?style=for-the-badge)](https://github.com/ntxmproducts/kinoflux-editor/releases/tag/v0.1.2)
[![Windows 10 and 11, 64-bit](https://img.shields.io/badge/Windows-10%20%7C%2011-0f1218?style=for-the-badge&logo=windows&logoColor=0ea5e9)](#download)
[![macOS, Apple Silicon](https://img.shields.io/badge/macOS-Apple%20Silicon-0f1218?style=for-the-badge&logo=apple&logoColor=white)](#download)
[![100% offline](https://img.shields.io/badge/100%25-offline-14b8a6?style=for-the-badge)](#privacy-and-offline-promise)
[![53 tools](https://img.shields.io/badge/tools-53-6366f1?style=for-the-badge)](#the-53-tools)
[![License: proprietary](https://img.shields.io/badge/license-proprietary-b91c1c?style=for-the-badge)](#licence)

<p>
  <a href="#download"><b>Download</b></a> &nbsp;|&nbsp;
  <a href="#why-kinoflux-editor"><b>Why</b></a> &nbsp;|&nbsp;
  <a href="#features"><b>Features</b></a> &nbsp;|&nbsp;
  <a href="#the-53-tools"><b>Tools</b></a> &nbsp;|&nbsp;
  <a href="#screenshots"><b>Screenshots</b></a> &nbsp;|&nbsp;
  <a href="#install"><b>Install</b></a> &nbsp;|&nbsp;
  <a href="#privacy-and-offline-promise"><b>Privacy</b></a> &nbsp;|&nbsp;
  <a href="#faq"><b>FAQ</b></a>
</p>

<br/>

<img src="assets/hero.png" alt="KinoFlux Editor on Windows in dark mode, compressing three videos at once: two are done with their new sizes shown, one is at 20 percent" width="860" />

<p><sub>Drop your files in, pick one action, press go. Results appear next to the originals and your originals are never changed.</sub></p>

</div>

---

## Download

<div align="center">

[![Download for Windows](https://img.shields.io/badge/%E2%AC%87_Download-Windows%20installer-0ea5e9?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-Setup-0.1.2-x64.exe)
[![Download for macOS](https://img.shields.io/badge/%E2%AC%87_Download-macOS%20disk%20image-0f1218?style=for-the-badge&logo=apple&logoColor=white)](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-0.1.2-macos-arm64.dmg)

</div>

| Platform | File | Size | Requires |
|:---------|:-----|-----:|:---------|
| **Windows** | [`KinoFlux-Editor-Setup-0.1.2-x64.exe`](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-Setup-0.1.2-x64.exe) | 262 MB (275,236,457 bytes) | Windows 10 (1809) or 11, 64-bit |
| **macOS** | [`KinoFlux-Editor-0.1.2-macos-arm64.dmg`](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-0.1.2-macos-arm64.dmg) | about 344 MB (360,250,711 bytes) | Apple Silicon (M1 or newer), macOS 11 or later |
| **Both** | [Release page for v0.1.2](https://github.com/ntxmproducts/kinoflux-editor/releases/tag/v0.1.2) | | Release notes and all files |

**SHA-256 checksums** (compare them with your download before you run it):

```text
50541c91e5b208b604da20adf601f6c47cc88c3d17e509f6ee79485859673529  KinoFlux-Editor-Setup-0.1.2-x64.exe
1b20312705c34f21c78f77f18e6d8cd363d90610c3ce1845daf988c8edb02a9c  KinoFlux-Editor-0.1.2-macos-arm64.dmg
```

```text
Windows (Command Prompt):  certutil -hashfile KinoFlux-Editor-Setup-0.1.2-x64.exe SHA256
macOS (Terminal):          shasum -a 256 KinoFlux-Editor-0.1.2-macos-arm64.dmg
```

> [!NOTE]
> The builds are **not code-signed** yet, and the Mac app is **not notarized**. Windows SmartScreen and macOS Gatekeeper will warn you on the first start. Both warnings are expected and the steps to continue are in [Install](#install). It takes about a minute, once.

KinoFlux Editor is **free to download and use**, with no subscription, no watermark and no account. It is proprietary software, not open source: see [Licence](#licence).

---

## Why KinoFlux Editor

Everyday file jobs (shrink a video for email, cut a clip, merge two PDFs, turn Word into PDF, strip location data from photos) usually end up on a website that wants your files, or in a big suite that wants a subscription. KinoFlux Editor is one small native window that does these jobs on your own computer.

| The usual way | With KinoFlux Editor |
|:--------------|:---------------------|
| Upload private files to a converter website | Files are converted **on your computer**. Nothing is uploaded, ever |
| Create an account, accept cookies, watch a size limit | No account, no limits from a server, works with the network switched off |
| A different site or app for video, audio, images, PDFs | **53 tools** for all five in one window |
| Learn a timeline editor to make one simple cut | Plain-language options: pick the action, press the button |
| Results that replace your original | New files next to the originals. Originals are never overwritten |

KinoFlux Editor is a **batch toolbox, not a multi-track timeline editor**: one action at a time on a list of files.

---

## Features

<table>
<tr>
<td width="50%" valign="top">

**One window, one flow**<br/>
Drop files or folders in, the right panel shows one action (preselected from the file type) and only its options. Press <kbd>Ctrl</kbd>+<kbd>Enter</kbd>.

**Command palette**<br/>
<kbd>Ctrl</kbd>+<kbd>K</kbd> (<kbd>Cmd</kbd>+<kbd>K</kbd> on macOS) opens a type-to-filter list of all 53 tools.

**Batch by default**<br/>
Multi-select, drag to reorder, progress per file and overall, cancel any time.

**Presets and history**<br/>
Save your favourite options per tool. A results list keeps your last 200 jobs with Open and Show buttons.

</td>
<td width="50%" valign="top">

**Native and light**<br/>
Written in Rust with the GPUI toolkit. No webview, no Electron. Light, dark or follow the system theme.

**Proven engines**<br/>
FFmpeg for video and audio, ImageMagick for images, qpdf and Poppler for PDFs, LibreOffice for documents. All bundled.

**Plain-language errors**<br/>
Wrong password, damaged file, disk full, permission denied: the message says what happened in normal words.

**Safe by design**<br/>
Programs are started with argument lists, never a shell string. Results are written as `.part` files and renamed on success, and existing files are never overwritten.

</td>
</tr>
</table>

---

## The 53 tools

| Area | Tools | Powered by |
|:-----|------:|:-----------|
| **Video** | 15 | FFmpeg |
| **Audio** | 6 | FFmpeg |
| **Image** | 7 | ImageMagick |
| **PDF** | 12 | qpdf, Poppler, native Rust |
| **Documents** | 13 | LibreOffice (bundled on Windows and macOS) |

Open an area to see every tool. The **CLI name** is what you pass to `--tool` on the command line (see [Command line](#command-line)). Every option, choice and default is listed in [docs/TOOLS.md](docs/TOOLS.md).

<details>
<summary><b>Video (15 tools)</b> &nbsp;<sub>mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv</sub></summary>
<br/>

| Tool | What it does | CLI name |
|:-----|:-------------|:---------|
| **Convert / compress** | Change format, quality or resolution in one step (MP4, MKV, WebM, MOV and more; H.264 or H.265; CPU or GPU encoder). | `video-convert` |
| **Compress** | Make a video much smaller with a light, medium or strong level, or hit a target size in MB. The bitrate is capped so the result does not grow. | `video-compress` |
| **Change format** | Switch container: MP4, MKV, WebM, MOV, M4V, AVI, FLV, WMV, MPEG or 3GP. Re-encode, or fast copy with no quality loss. | `video-format` |
| **Change resolution** | Scale from 4K (2160p) down to 144p. Enlarging smaller videos is optional. | `video-resolution` |
| **Trim** | Cut a part out of a video, with a thumbnail strip, fast (stream copy) or precise (re-encode) mode. | `video-trim` |
| **Change speed** | Fast forward or slow motion from 0.25x to 16x, with the pitch of the sound kept. | `video-speed` |
| **Remove audio** | Delete the sound track without re-encoding the picture. | `video-remove-audio` |
| **Join videos** | Put several videos one after another into ONE file (order = list order). Different sizes and codecs are fine. | `video-merge` |
| **Stream package (HLS)** | Split a video into .m3u8 segments for web streaming, one quality or a ladder (1080p to 360p). | `video-hls` |
| **Extract audio** | Save the sound of a video as MP3, M4A, Opus, OGG, FLAC, WAV, AAC, WMA, AC3, MP2, AIFF or an iPhone ringtone (M4R). | `video-extract-audio` |
| **Make a GIF** | Turn a part of a video into an animated GIF (start, length, width, frames per second). | `video-gif` |
| **Replace / mix audio** | Put a different sound track on a video, or mix a new one in. | `video-replace-audio` |
| **Rotate / flip** | Turn a sideways video upright or mirror it. | `video-rotate` |
| **Burn in subtitles** | Burn an .srt or .ass subtitle file onto the picture. | `video-subtitles` |
| **Save a frame as picture** | Grab a still image from a video. | `video-frame` |

</details>

<details>
<summary><b>Audio (6 tools)</b> &nbsp;<sub>mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif</sub></summary>
<br/>

| Tool | What it does | CLI name |
|:-----|:-------------|:---------|
| **Convert** | Change format, bitrate, sample rate or channels. | `audio-convert` |
| **Trim** | Cut a part out of an audio file. | `audio-trim` |
| **Volume / normalize** | Make quiet files louder and even out loudness. | `audio-volume` |
| **Change speed** | Faster or slower playback without changing the pitch. | `audio-speed` |
| **Join audio files** | Put several recordings one after another into ONE file (order = list order). | `audio-merge` |
| **Fade in / out** | Smooth fade in and fade out. | `audio-fade` |

</details>

<details>
<summary><b>Image (7 tools)</b> &nbsp;<sub>jpg, png, webp, bmp, tif, gif, ico, heic, heif, avif, jp2, tga, psd, svg</sub></summary>
<br/>

| Tool | What it does | CLI name |
|:-----|:-------------|:---------|
| **Convert / compress** | Change format, lower quality or limit the size (JPG, PNG, WebP and more). | `image-convert` |
| **Compress** | Make pictures smaller with a simple quality level. | `image-compress` |
| **Resize** | Scale by percent, width, height or to a box. | `image-resize` |
| **Resize to a preset** | Ready-made sizes for Instagram, YouTube, X, Facebook, passport photos and more. | `image-preset` |
| **Crop / rotate** | Crop to a shape, rotate or flip. | `image-crop-rotate` |
| **Add a watermark** | Stamp text or a logo on pictures. | `image-watermark` |
| **Remove metadata** | Delete EXIF data, GPS location and camera info. | `image-strip` |

HEIC and HEIF files can be read but not written. SVG is read but not offered as an output.

</details>

<details>
<summary><b>PDF (12 tools)</b> &nbsp;<sub>pdf, plus pictures for "Pictures to PDF"</sub></summary>
<br/>

| Tool | What it does | CLI name |
|:-----|:-------------|:---------|
| **Merge** | Join several PDFs into ONE file (order = list order). | `pdf-merge` |
| **Extract / remove / split pages** | Keep, remove or split pages (for example one file per page). | `pdf-pages` |
| **Pages to pictures** | Save PDF pages as PNG or JPG pictures. | `pdf-to-images` |
| **Extract text** | Save the text of a PDF as a .txt file. | `pdf-to-text` |
| **Rotate pages** | Turn all pages or only some pages. | `pdf-rotate` |
| **Compress** | Shrink the pictures inside a PDF (scans, photos). | `pdf-compress` |
| **Optimize (lossless)** | Reduce PDF size losslessly, with no loss of quality. | `pdf-optimize` |
| **Add a text watermark** | Stamp CONFIDENTIAL, DRAFT or your own text on every page. | `pdf-watermark` |
| **Add a password** | Encrypt a PDF so it asks for a password. | `pdf-protect` |
| **Remove the password** | Save an unlocked copy (you must know the password). | `pdf-unprotect` |
| **Remove document info** | Delete author, title and creation info. | `pdf-metadata` |
| **Pictures to PDF** | Make one PDF from one or many pictures. | `image-to-pdf` |

</details>

<details>
<summary><b>Documents (13 tools)</b> &nbsp;<sub>Word, Excel, PowerPoint, OpenDocument, RTF, TXT, CSV, HTML</sub></summary>
<br/>

| Tool | What it does | CLI name |
|:-----|:-------------|:---------|
| **PowerPoint to PDF** | Convert slides (PPT, PPTX, PPS, PPSX, ODP) to PDF. | `ppt-to-pdf` |
| **Word to PDF** | Convert documents (DOC, DOCX, ODT, RTF, TXT) to PDF. | `word-to-pdf` |
| **Excel to PDF** | Convert spreadsheets (XLS, XLSX, ODS, CSV) to PDF. | `excel-to-pdf` |
| **PDF to Word** | Make an editable .docx from a PDF (layout is approximate). | `pdf-to-word` |
| **PDF to PowerPoint** | Make an editable .pptx from a PDF (layout is approximate). | `pdf-to-slides` |
| **PDF to Excel** | Pull the text and tables of a PDF into an .xlsx (no OCR for scanned PDFs). | `pdf-to-sheet` |
| **Update old Office files** | Update old files: DOC to DOCX, XLS to XLSX, PPT to PPTX. | `office-modernize` |
| **Office to OpenDocument** | DOCX / XLSX / PPTX to ODT / ODS / ODP. | `office-to-odf` |
| **OpenDocument to Office** | ODT / ODS / ODP to DOCX / XLSX / PPTX. | `odf-to-office` |
| **Spreadsheet to CSV** | Save the first sheet of an Excel or ODS file as CSV. | `sheet-to-csv` |
| **CSV to spreadsheet** | Open a CSV as a real Excel or ODS file. | `csv-to-sheet` |
| **Document to HTML** | Save a Word / ODT / RTF / TXT document as a web page. | `doc-to-html` |
| **HTML to document** | Turn a web page file into .docx or .odt. | `html-to-doc` |

These 13 tools use LibreOffice. It is **included in the Windows installer and inside the Mac app**, so they work out of the box and there is nothing else to install.

</details>

---

## Screenshots

<div align="center">

<table>
<tr>
<td align="center" width="50%">
<img src="assets/screenshots/windows-video-trim.webp" alt="Video Trim tool with a thumbnail strip, a two-handle range slider, Start and End boxes and a cut mode choice" width="100%" /><br/>
<b>Trim</b><br/><sub>Thumbnail strip, Start and End boxes, fast or precise cut</sub>
</td>
<td align="center" width="50%">
<img src="assets/screenshots/windows-image-convert.webp" alt="Image Convert and compress tool with three pictures converted to smaller files" width="100%" /><br/>
<b>Images</b><br/><sub>Convert, compress, limit size, remove EXIF and GPS data</sub>
</td>
</tr>
<tr>
<td align="center">
<img src="assets/screenshots/windows-pdf-merge.webp" alt="PDF Merge tool with two PDF files in the list ready to be joined" width="100%" /><br/>
<b>PDF merge</b><br/><sub>Join files in the order of the list</sub>
</td>
<td align="center">
<img src="assets/screenshots/windows-documents-to-pdf.webp" alt="Documents tool converting a DOCX and an ODT file to PDF" width="100%" /><br/>
<b>Documents to PDF</b><br/><sub>Word, Excel and PowerPoint without Office</sub>
</td>
</tr>
<tr>
<td align="center">
<img src="assets/screenshots/windows-extract-audio.webp" alt="Extract audio tool turning a video into an MP3 file with a bitrate option" width="100%" /><br/>
<b>Extract audio</b><br/><sub>MP3, M4A, FLAC, WAV, Opus and more</sub>
</td>
<td align="center">
<img src="assets/screenshots/windows-command-palette.webp" alt="The command palette open with a search box and a list of tools" width="100%" /><br/>
<b>Command palette</b><br/><sub>Ctrl+K and type what you want to do</sub>
</td>
</tr>
<tr>
<td align="center">
<img src="assets/screenshots/windows-results-history.webp" alt="The Recent results list showing finished jobs for documents, PDF, image and video tools" width="100%" /><br/>
<b>Results history</b><br/><sub>Your last 200 jobs, with Open and Show</sub>
</td>
<td align="center">
<img src="assets/screenshots/presets.webp" alt="Video Compress with Target a file size set to 25 MB and the saved presets Email 25 MB and Small 720p shown under the options" width="100%" /><br/>
<b>Presets</b><br/><sub>Save the options you use all the time, then apply them in one click</sub>
</td>
</tr>
<tr>
<td align="center">
<img src="assets/screenshots/windows-target-size-done.webp" alt="Video Compress with the Target a file size option: a 151 MB video reduced to 18.5 MB" width="100%" /><br/>
<b>Compress to a target size</b><br/><sub>Ask for a number of MB and get close to it</sub>
</td>
<td align="center">
<img src="assets/screenshots/windows-pdf-split.webp" alt="PDF Extract, remove and split pages with the option to split into one file per page" width="100%" /><br/>
<b>Split a PDF</b><br/><sub>Keep, remove or split pages</sub>
</td>
</tr>
</table>

<br/>

<b>Light, dark and macOS</b>

<table>
<tr>
<td align="center" width="33%">
<img src="assets/screenshots/windows-light-theme.webp" alt="KinoFlux Editor on Windows in the light theme" width="100%" /><br/>
<sub>Windows, light theme</sub>
</td>
<td align="center" width="33%">
<img src="assets/screenshots/macos-dark.webp" alt="KinoFlux Editor on macOS in the dark theme" width="100%" /><br/>
<sub>macOS, dark theme</sub>
</td>
<td align="center" width="33%">
<img src="assets/screenshots/macos-light.webp" alt="KinoFlux Editor on macOS in the light theme" width="100%" /><br/>
<sub>macOS, light theme</sub>
</td>
</tr>
<tr>
<td align="center">
<img src="assets/screenshots/macos-command-palette.webp" alt="The command palette on macOS opened with Cmd+K" width="100%" /><br/>
<sub>macOS, command palette (Cmd+K)</sub>
</td>
<td align="center">
<img src="assets/screenshots/macos-done.webp" alt="Finished jobs on macOS with the size saved shown in green" width="100%" /><br/>
<sub>macOS, finished jobs</sub>
</td>
<td align="center">
<img src="assets/screenshots/windows-narrow-layout.webp" alt="The narrow stacked layout with the file list above the tool panel" width="60%" /><br/>
<sub>Narrow windows stack the layout</sub>
</td>
</tr>
</table>

</div>

---

## Install

### Windows

<table>
<tr>
<td valign="top" width="60%">

1. [Download the installer](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-Setup-0.1.2-x64.exe) and (optionally) check its [SHA-256](#download).
2. Run it. If Windows shows **"Windows protected your PC"** (SmartScreen, because the installer is not code-signed yet), click **More info**, then **Run anyway**.
3. Choose **this user only** (default, no administrator prompt) or all users. Optional extras: a desktop icon and right-click **Open with KinoFlux Editor** entries.
4. Start **KinoFlux Editor** from the Start menu.

**Silent install:** `KinoFlux-Editor-Setup-0.1.2-x64.exe /VERYSILENT /CURRENTUSER`

</td>
<td valign="top" width="40%" align="center">
<img src="assets/screenshots/windows-installer-welcome.webp" alt="The Windows setup wizard welcome page for KinoFlux Editor 0.1.2" width="100%" /><br/><br/>
<img src="assets/screenshots/windows-installer-tasks.webp" alt="The Windows setup wizard tasks page with optional desktop icon and Open with KinoFlux Editor entries" width="100%" />
</td>
</tr>
</table>

### macOS (Apple Silicon)

<table>
<tr>
<td valign="top" width="55%">

1. [Download the disk image](https://github.com/ntxmproducts/kinoflux-editor/releases/download/v0.1.2/KinoFlux-Editor-0.1.2-macos-arm64.dmg), open it and drag **KinoFlux Editor** onto **Applications**.
2. Open the app. macOS says **"KinoFlux Editor" Not Opened** because the app is ad-hoc signed but not notarized by Apple. Click **Done** (not *Move to Bin*).
3. Open **System Settings > Privacy & Security**, scroll to **"KinoFlux Editor was blocked"** and press **Open Anyway** (macOS 15 and newer). On macOS 14 and older, right-click the app and choose **Open**.
4. Or do the same in Terminal:

```bash
xattr -dr com.apple.quarantine "/Applications/KinoFlux Editor.app"
```

You only need to do this once.

**Documents tools on macOS:** LibreOffice 26.2.6 (the official build, unmodified) is bundled inside the app, so the 13 Documents tools work out of the box. There is nothing else to install.

</td>
<td valign="top" width="45%" align="center">
<img src="assets/screenshots/macos-dmg-window.webp" alt="The macOS disk image window with the app icon and an arrow to the Applications folder" width="100%" /><br/><br/>
<img src="assets/screenshots/macos-gatekeeper.webp" alt="The macOS dialog saying KinoFlux Editor was not opened because Apple could not verify it, with Done and Move to Bin buttons" width="70%" />
</td>
</tr>
</table>

### System requirements

| | Windows | macOS |
|:--|:--------|:------|
| **System** | Windows 10 (version 1809) or Windows 11, 64-bit | macOS 11 or later (tested on macOS 26.6) |
| **Processor** | x64 | Apple Silicon (M1 or newer). Intel Macs are not supported |
| **Graphics** | Direct3D 11 (the interface is drawn by GPUI) | Metal |
| **Disk space** | About 1.1 GB after installation (all helper programs and LibreOffice are included) | About 1 GB after installation (all helper programs and LibreOffice are included; the disk image is about 344 MB) |
| **Network** | Not needed | Not needed |

### Uninstall

- **Windows:** Settings > Apps > KinoFlux Editor > Uninstall. The uninstaller asks whether to also delete your settings, history and logs (silent uninstall: `/REMOVEDATA` removes them).
- **macOS:** drag the app to the Trash. To also remove settings, history, logs and caches:

```bash
rm -rf ~/Library/Application\ Support/KinoFlux\ Editor ~/Library/Logs/KinoFlux\ Editor ~/Library/Caches/KinoFlux\ Editor ~/Library/Preferences/org.ntxm.kinoflux-editor.plist
```

Your converted files are never touched by an uninstall.

---

## Privacy and offline promise

<div align="center">

| | |
|:--|:--|
| **No network code** | The program never opens a connection. No accounts, no telemetry, no analytics, no crash upload, **no update check** |
| **Your files stay put** | Everything is converted on your computer by bundled programs. Nothing is uploaded and originals are never changed |
| **Nothing sensitive stored** | Only settings, presets, history, logs and crash reports are written, in per-user folders. No file contents and no passwords |

</div>

You can disconnect from the internet and everything still works. Because there is no update check, **new versions are not announced inside the app**: watch the [releases page](https://github.com/ntxmproducts/kinoflux-editor/releases) or [ntxm.org](https://ntxm.org/products/kinoflux/videoeditor/) when you want to update.

**How "no network" was checked** (details in [docs/DATA_HANDLING.md](docs/DATA_HANDLING.md)):

1. A dependency audit of the Windows and macOS builds found no HTTP client, TLS library or networking stack in the app.
2. The Windows executable imports no internet libraries (`winhttp`, `wininet`, `urlmon`).
3. A runtime spot check on Windows 11 watched the app and its helper programs during a real conversion: no network endpoint was opened.

To be precise: bundled FFmpeg, Poppler and LibreOffice contain network features of their own. KinoFlux Editor only hands them local files and starts LibreOffice headless, so those features are not reachable from the app. That is a design guarantee, not an operating-system sandbox. If you need a hard guarantee, block the program in your firewall.

Policies: [Privacy Policy](PRIVACY.md) | [Terms](TERMS.md) | [Licence](LICENSE) | [Third-party notices](THIRD_PARTY_NOTICES.md). They are also readable inside the app (press <kbd>F1</kbd>).

### Where your data lives

| What | Windows | macOS |
|:-----|:--------|:------|
| Settings, presets, history (last 200 jobs) | `%APPDATA%\KinoFlux Editor` | `~/Library/Application Support/KinoFlux Editor` |
| Logs and crash reports | `%LOCALAPPDATA%\KinoFlux Editor\logs` | `~/Library/Logs/KinoFlux Editor` |

You can look at these folders, copy them or delete them at any time. Crash reports are never sent anywhere.

<div align="center">
<img src="assets/screenshots/windows-privacy-policy.webp" alt="The Privacy Policy page inside the app, stating that KinoFlux Editor works completely offline" width="720" />
<p><sub>The privacy policy is part of the app (F1 > Privacy).</sub></p>
</div>

---

## Using it

1. **Add files:** drop files or folders on the window, press <kbd>Ctrl</kbd>+<kbd>O</kbd>, or start the program with files as arguments.
2. **Pick the action:** the right panel is preselected from the file type. Switch it with the button or <kbd>Ctrl</kbd>+<kbd>K</kbd>.
3. **Go:** press <kbd>Ctrl</kbd>+<kbd>Enter</kbd>. Progress shows inline in every file row, <kbd>Esc</kbd> cancels.
4. **Find the result:** new files are written next to the originals as `name_converted.mp4`, `name_merged.pdf` and so on (` (2)` is added if the name exists), or into a folder you choose under **Save to**.

### Keyboard shortcuts

| Keys | Action |
|:-----|:-------|
| <kbd>Ctrl</kbd>+<kbd>O</kbd> / <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>O</kbd> | Add files / add a folder |
| <kbd>Ctrl</kbd>+<kbd>K</kbd> | Action palette (also: add files, clear finished, change theme) |
| <kbd>Ctrl</kbd>+<kbd>Enter</kbd> | Start (or cancel while running) |
| <kbd>Esc</kbd> | Close the palette / cancel running jobs |
| <kbd>F1</kbd> | About, help and legal pages |
| <kbd>Ctrl</kbd>+<kbd>A</kbd>, arrows, click, <kbd>Ctrl</kbd>+click, <kbd>Shift</kbd>+click | Select files |
| <kbd>Delete</kbd> | Remove the selected rows |
| Drag a row, or <kbd>Alt</kbd>+<kbd>Up</kbd> / <kbd>Alt</kbd>+<kbd>Down</kbd> | Reorder (this sets the join and merge order) |
| <kbd>Tab</kbd> / <kbd>Shift</kbd>+<kbd>Tab</kbd> | Move between controls |

On macOS read <kbd>Cmd</kbd> for <kbd>Ctrl</kbd>. Also on macOS: <kbd>Cmd</kbd>+<kbd>Q</kbd> quits, <kbd>Cmd</kbd>+<kbd>H</kbd> hides, <kbd>Cmd</kbd>+<kbd>W</kbd> closes the window and <kbd>Cmd</kbd>+<kbd>M</kbd> minimizes. Drag the thin splitter between the list and the panel to resize it (double-click resets). The moon/sun button at the bottom right cycles system, light and dark.

### Command line

```text
kinoflux-editor [--tool <cli-name>] [--start] [--new-instance] [files or folders...]

kinoflux-editor --tool pdf-merge --start a.pdf b.pdf
```

A second start hands its files to the already running window unless `--new-instance` is given. The CLI names are in the tool tables above.

---

## FAQ

<details>
<summary><b>Is KinoFlux Editor free?</b></summary>
<br/>
Yes. It is free to download and use: no subscription, no watermark on results and no account. It is proprietary software (not open source), (c) 2026 ntxm.org. The licence lets you install and run it on computers you control for personal or internal business use, including processing files for paying clients. Redistribution is limited to the official, unmodified installer or package. See <a href="LICENSE">LICENSE</a>.
</details>

<details>
<summary><b>Does it need the internet, or upload my files?</b></summary>
<br/>
No. Your files are converted on your computer by the bundled programs. The app has no accounts, no telemetry, no analytics, no crash upload and no update check, and it never opens a network connection.
</details>

<details>
<summary><b>Does it overwrite my original files?</b></summary>
<br/>
Never. Results are written as new files next to the originals (for example <code>clip_converted.mp4</code> or <code>report_merged.pdf</code>), with " (2)" added if the name already exists, or into a folder you choose under "Save to".
</details>

<details>
<summary><b>Is this a timeline video editor?</b></summary>
<br/>
No. It is a batch toolbox for everyday jobs: convert, compress, trim, join, change speed, rotate, make GIFs, burn in subtitles, extract or replace audio and more. One action at a time on a list of files, not a multi-track timeline.
</details>

<details>
<summary><b>Windows says "Windows protected your PC". Is the file safe?</b></summary>
<br/>
The installer and the program are not code-signed yet, so Microsoft SmartScreen may warn about an unknown publisher. Click <b>More info</b>, then <b>Run anyway</b>. You can compare the SHA-256 of your download with the value in <a href="#download">Download</a> before you run it.
</details>

<details>
<summary><b>macOS says KinoFlux Editor "Not Opened". What do I do?</b></summary>
<br/>
The Mac app is ad-hoc signed but not notarized by Apple, so Gatekeeper blocks the first start. Click <b>Done</b> (not Move to Bin), open <b>System Settings > Privacy & Security</b>, scroll to "KinoFlux Editor was blocked" and press <b>Open Anyway</b> (macOS 15 and newer). On macOS 14 and older, right-click the app and choose Open. You only need to do this once. The Terminal alternative is in <a href="#install">Install</a>.
</details>

<details>
<summary><b>Do the Documents tools work on my Mac?</b></summary>
<br/>
Yes. The Mac app includes LibreOffice 26.2.6 (the official build from The Document Foundation, unmodified), so the 13 Documents tools work out of the box. If they ever show a notice that LibreOffice was not found, download the disk image again and reinstall the app. On Windows LibreOffice is included in the installer too.
</details>

<details>
<summary><b>Which systems are supported?</b></summary>
<br/>
Windows 10 (1809) and Windows 11, 64-bit, and Macs with Apple Silicon (M1 or newer) running macOS 11 or later. Intel Macs, Windows on ARM and Linux are not offered at the moment.
</details>

<details>
<summary><b>Which formats can it read and write?</b></summary>
<br/>
The accepted input formats per area are listed above each tool table, and every tool's output choices are in <a href="docs/TOOLS.md">docs/TOOLS.md</a>. Examples: MP4, MKV, WebM, MOV and GIF for video; MP3, M4A, FLAC, WAV and Opus for audio; JPG, PNG, WebP and more for images; PDF, DOCX, XLSX, PPTX and ODF for documents.
</details>

<details>
<summary><b>How do I update?</b></summary>
<br/>
The app never checks for updates, so it will not tell you. Download the newer installer or disk image from the <a href="https://github.com/ntxmproducts/kinoflux-editor/releases">releases page</a> and install it. Your own files are never touched.
</details>

<details>
<summary><b>Where are my settings and how do I remove them?</b></summary>
<br/>
See <a href="#where-your-data-lives">Where your data lives</a> and <a href="#uninstall">Uninstall</a>. The Windows uninstaller can delete them for you.
</details>

<details>
<summary><b>Can I redistribute it or put it on my own website?</b></summary>
<br/>
You may redistribute only the official, unmodified installer or package, under its correct name and branding, with a statement that it is proprietary to ntxm.org. Nothing else. Read <a href="LICENSE">LICENSE</a> for the exact terms.
</details>

---

## Known limitations

Being straight about what 0.1.2 does not do:

- **Unsigned builds.** The Windows installer is not code-signed (SmartScreen warns). The Mac app is ad-hoc signed and **not notarized** (a one-time Gatekeeper step is needed).
- **Platforms.** Windows 10/11 x64 and macOS on Apple Silicon only. No Intel Mac, Windows ARM64 or Linux builds yet.
- **Larger Mac download.** LibreOffice is bundled in the Mac app, so the disk image is about 344 MB and the app is about 1 GB once installed.
- **Trim range slider.** In the 0.1.2 launch tests, dragging the range slider updated the Start and End boxes but the finished file was still the full length; typing the times into the **Start** and **End** boxes worked. Until that is fixed, type the times. The thumbnails and slider are still handy for finding the moment. Details: [Trim a video without re-encoding](https://ntxm.org/blogs/kinoflux-editor/trim-video-without-re-encoding/).
- **Fast trim** copies the stream and starts at the previous keyframe, so the cut can begin a little early. Use **Precise** for exact cuts.
- **PDF compress** works on the pictures inside a PDF; text-only PDFs barely change (use **Optimize** for a lossless pass).
- **PDF to Word / PowerPoint** are editable but the layout is approximate. **PDF to Excel** reads real text, so scanned PDFs give an empty result (no OCR).
- **Spreadsheet to CSV** exports the first sheet only.
- **HEIC / HEIF** can be read but not written. **SVG** is not offered as an output. **OGV** is read but not written.
- **PDF passwords** are passed to `qpdf` on its command line, so other programs running as the same user could see them while that one job runs. They are never saved.
- **Documents (LibreOffice) jobs run one at a time.** Other areas run in parallel.
- **No automatic updates**, by design (see [Privacy](#privacy-and-offline-promise)).

---

## What's new in 0.1.2

*Released 2026-10-03. The first release of the native (Rust + GPUI) KinoFlux Editor.*

- **53 tools** in five areas: Video 15, Audio 6, Image 7, PDF 12, Documents 13, all offline.
- **One window**: drag-and-drop file list, multi-select, reorder, command palette, presets per tool, results history, progress per file and overall, cancel.
- **Trim preview** with a thumbnail strip and range slider.
- **Light, dark or system theme**; remembers window size, panel width and last options. Draggable splitter, stacked layout in narrow windows.
- **Plain-language error messages** and an **About window** (F1) with Help, Privacy, Terms, Licence, Third-party notices and Data handling.
- **Windows installer**: per user or all users, Start menu entry, optional desktop icon and right-click entries, optional removal of your data on uninstall, silent install.
- **macOS (Apple Silicon)**: menu bar, Cmd shortcuts, Finder / Dock / Open With file opening, Retina support, helper programs (LibreOffice included) bundled inside the app. All 53 tools passed 173 end-to-end cases on a Mac (macOS 26.6).
- **Offline and private by design**: no network code, no telemetry, no account, no update check.
- Bundled programs: FFmpeg 8.0 (GPL v3 build), ImageMagick 7.1.2-11, qpdf 12.2.0, Poppler 26.09.0, LibreOffice Portable 26.2.1.2 (Windows), LibreOffice 26.2.6 (macOS).

Full history: [CHANGELOG.md](CHANGELOG.md).

---

## Third-party software

KinoFlux Editor itself is proprietary. It ships with independent programs that **keep their own licences**:

| Program | Used for | Licence |
|:--------|:---------|:--------|
| [FFmpeg](https://ffmpeg.org/) 8.0 (GPL v3 build) | Video and audio | GNU GPL v3 or later |
| [ImageMagick](https://imagemagick.org/) 7.1.2-11 | Images | ImageMagick License (Apache-2.0 style) |
| [qpdf](https://github.com/qpdf/qpdf) 12.2.0 | PDF merge, split, protect | Apache-2.0 |
| [Poppler](https://poppler.freedesktop.org/) 26.09.0 | PDF to pictures and text | GNU GPL v2 or later |
| [LibreOffice](https://www.libreoffice.org/) 26.2.1.2 (Windows), 26.2.6 (macOS) | Documents tools | MPL-2.0 and LGPL-3.0-or-later |
| Rust libraries | The app itself | MIT, Apache-2.0 and others |

KinoFlux Editor starts these programs as separate processes; it does not contain their code. **Source-code offer:** for at least three years from the day you received KinoFlux Editor, ntxm.org will send you the complete corresponding source code of the GPL-licensed programs in the package (FFmpeg and Poppler) on request, for no more than the cost of copying. Write to **contact@ntxm.org**. Full texts, versions and links: [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). KinoFlux Editor is not affiliated with or endorsed by The Document Foundation, FFmpeg, ImageMagick Studio, qpdf or the Poppler project.

---

## Support

| | |
|:--|:--|
| **Questions and bugs** | [Open an issue](https://github.com/ntxmproducts/kinoflux-editor/issues/new/choose) (please do not attach private files) |
| **Email** | [contact@ntxm.org](mailto:contact@ntxm.org) |
| **Security reports** | [SECURITY.md](SECURITY.md) |
| **Product page** | [ntxm.org/products/kinoflux/videoeditor](https://ntxm.org/products/kinoflux/videoeditor/) |
| **Guides and notes** | [ntxm.org/blogs](https://ntxm.org/blogs/) |

**Guides:**
[What KinoFlux Editor 0.1.2 is](https://ntxm.org/blogs/kinoflux-editor/introducing-kinoflux-editor-0-1-2/) |
[Install on Windows and macOS](https://ntxm.org/blogs/kinoflux-editor/install-kinoflux-editor-windows-macos/) |
[Compress to a target size](https://ntxm.org/blogs/kinoflux-editor/compress-video-to-a-target-size/) |
[Trim without re-encoding](https://ntxm.org/blogs/kinoflux-editor/trim-video-without-re-encoding/) |
[Extract audio](https://ntxm.org/blogs/kinoflux-editor/extract-audio-from-a-video/) |
[Convert images in bulk](https://ntxm.org/blogs/kinoflux-editor/convert-and-resize-images-in-bulk/) |
[Merge, split and compress PDFs](https://ntxm.org/blogs/kinoflux-editor/merge-split-and-compress-pdfs-offline/) |
[Word to PDF without Office](https://ntxm.org/blogs/kinoflux-editor/convert-word-documents-to-pdf-offline/) |
[Shortcuts, presets and history](https://ntxm.org/blogs/kinoflux-editor/keyboard-shortcuts-presets-and-history/) |
[What it does with your files](https://ntxm.org/blogs/kinoflux-editor/what-kinoflux-editor-does-with-your-files/)

---

## Licence

KinoFlux Editor is **proprietary software**, Copyright (c) 2026 ntxm.org. All rights reserved. **This repository is a release and showcase page: it contains the documentation, images and policies, not the source code.**

| You may | You may not (without written permission) |
|:--------|:-----------------------------------------|
| Download and use the app free of charge, personally or for your own business work | Copy, publish or share the source code or non-installer binaries |
| Redistribute the **official, unmodified** installer or package under its correct name and branding | Modify, repackage, rebrand, sell, rent or sublicense it |
| Keep all the rights the third-party licences give you for the bundled programs | Reverse engineer it (except where the law says you always may), or remove notices |

The software is provided "as is", without warranty. The legally binding text is [LICENSE](LICENSE); the plain-language summary is [TERMS.md](TERMS.md). A public repository does not make this open source.

---

<div align="center">

<img src="assets/logo.png" alt="KinoFlux Editor icon" width="56" />

**KinoFlux Editor** 0.1.2 is made by **[ntxm.org](https://ntxm.org)**

Fast. Local. Private.

[Download](#download) | [Releases](https://github.com/ntxmproducts/kinoflux-editor/releases) | [Product page](https://ntxm.org/products/kinoflux/videoeditor/) | [Privacy](PRIVACY.md) | [Licence](LICENSE) | [ntxm.org](https://ntxm.org)

<sub>(c) 2026 ntxm.org. KinoFlux is a product name of ntxm.org.</sub>

</div>
