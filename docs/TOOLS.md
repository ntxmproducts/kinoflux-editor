# KinoFlux Editor 0.1.2: tool reference

All 53 tools, every option and its default. The per-tool tables are generated from the program's own tool list, so option names, choices and defaults are exactly what the interface shows. The **slug** in brackets is what you pass to `--tool` on the command line.

| Area | Tools | Engine |
|------|------:|--------|
| Video | 15 | FFmpeg |
| Audio | 6 | FFmpeg |
| Image | 7 | ImageMagick |
| PDF | 12 | qpdf, Poppler (`pdftoppm`, `pdftotext`), native Rust |
| Documents | 13 | LibreOffice (headless) + Poppler |

Results are written as `name_<suffix>.<ext>` next to the original (or into the folder you choose), never overwriting an existing file (` (2)` is appended), as a `.part` file that is renamed on success. Programs are always started with an argument list, never a shell string.

## Decisions that affect behaviour

* **No Ghostscript.** PDF compression is done natively: the PDF is opened with `lopdf`, JPEG images are decoded and
  re-encoded at lower quality / size, then the file is saved with a fixed cross-reference table. Text-only PDFs
  barely change (use *Optimize* for a lossless pass).
* **Video Compress never makes a file bigger**: the video bitrate is capped at 85% of the source bitrate
  (found by a 4K screen recording that grew after "Medium").
* **Fast trim** (stream copy) starts at the **previous keyframe**, so the first seconds can be a little early.
  Use *Precise* for exact cuts. The trim preview shows 10 thumbnails and a two-handle slider.
* **Join videos / audio re-encode** (works for different sizes/codecs) instead of risky stream copy.
* **HLS** writes a flat folder `name_hls/` with `index.m3u8` and `seg_000.ts`...
* **OGV output was removed**: the bundled FFmpeg 8.0 libtheora produces inter-frames that do not decode. OGV is still read.
* **HEIC/HEIF** can be read (bundled ImageMagick) but not written. **SVG** is not offered as an output.
* **Subtitles**: a subtitle path containing a `'` is refused (FFmpeg filter quoting); everything else is escaped.
* **PDF passwords** are passed to `qpdf` on its command line (visible to other programs of the same user
  while the job runs); they are never written to settings or history. Locked PDFs are detected up front and give
  *Use "PDF - Remove the password" first.*
* **PDF -> Excel** uses `pdftotext -layout`, splits columns at 2+ spaces, imports the CSV with LibreOffice and saves .xlsx
  (LibreOffice's own PDF import turns text into pictures). Scanned PDFs have no text, so the result is empty (no OCR).
* **PDF -> Word / PowerPoint** use LibreOffice's Draw import: editable, but layout is approximate.
* **LibreOffice jobs run one at a time** (one profile directory per run, group lock); all other areas run in parallel
  (Video 2, Audio 3, Image 4, PDF 3).
* **CSV export** uses comma, no quoting of plain text, UTF-8; **first sheet only**.
* **FFmpeg 8.0 quirk:** Opus in WebM/MKV prints one harmless "Error parsing Opus packet header" line.


## Video (15 tools)

### Video - Convert / compress  (`video-convert`)

Change format, shrink the file size or resolution. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Format | MP4 - plays everywhere / MKV - flexible container / WebM - for the web (VP9 + Opus) / MOV - QuickTime / M4V - Apple video / AVI - older players / FLV - Flash video / WMV - Windows Media / MPEG - DVD style / 3GP - old phones | MP4 - plays everywhere |
| Video codec _(when format = mp4/mkv/mov/m4v)_ | H.264 - most compatible / H.265 / HEVC - smaller files | H.264 - most compatible |
| Quality | Smaller file / Balanced / High quality | Balanced |
| Size | Keep original size / 4K (2160p) / 1440p / 1080p / 720p / 480p / 360p | Keep original size |
| Audio | Keep audio / Remove audio | Keep audio |
| Encoder _(when format = mp4/mkv/mov/m4v)_ | CPU (best compression) / GPU (fastest) | CPU (best compression) |

### Video - Compress  (`video-compress`)

Make a video much smaller, or hit a target size in MB. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Compression | Light - barely visible loss / Medium - good balance / Strong - much smaller / Target a file size | Medium - good balance |
| Target size _(when level = target)_ | 1 to 20000 MB | 25 |
| Video codec | H.264 - most compatible / H.265 / HEVC - smaller files | H.264 - most compatible |
| Largest size | Keep original size / 1080p / 720p / 480p | Keep original size |
| Encoder _(when level = light/medium/strong)_ | CPU (best compression) / GPU (fastest) | CPU (best compression) |

### Video - Change format  (`video-format`)

MP4, MKV, WebM, MOV, AVI, FLV, WMV, MPEG, 3GP, OGV. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Format | MP4 / MKV / WebM / MOV / M4V / AVI / FLV / WMV / MPEG / 3GP | MP4 |
| Method | Re-encode (always works) / Fast copy (no quality loss) | Re-encode (always works) |

### Video - Change resolution  (`video-resolution`)

Scale to 2160p ... 144p. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Height | 4K (2160p) / 1440p / 1080p (Full HD) / 720p (HD) / 480p / 360p / 240p / 144p | 720p (HD) |
| Allow enlarging smaller videos | on / off | off |
| Quality | Smaller file / Balanced / High quality | Balanced |

### Video - Trim  (`video-trim`)

Cut a part out of a video. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Start | text | 0:00 |
| End | text |  |
| Cut mode | Fast - no re-encoding (may start at the nearest keyframe) / Precise - re-encode (exact cut, slower) | Fast - no re-encoding (may start at the nearest keyframe) |

### Video - Change speed  (`video-speed`)

Fast forward or slow motion. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Speed | 0.25 to 16 x | 2 |
| Sound | Keep (speed adjusted, pitch kept) / Remove | Keep (speed adjusted, pitch kept) |
| Quality | Smaller file / Balanced / High quality | Balanced |

### Video - Remove audio  (`video-remove-audio`)

Delete the sound track without re-encoding. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

No options.

### Video - Join videos  (`video-merge`)

Put several videos one after another. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv. Joins all selected files into ONE result (order = list order).

| Option | Choices / range | Default |
|---|---|---|
| Size | Same as the first video / 1080p / 720p / 480p | Same as the first video |
| Quality | Smaller file / Balanced / High quality | Balanced |

### Video - Stream package (HLS)  (`video-hls`)

Split into .m3u8 segments for web streaming. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Qualities | One quality (same as the video) / Standard: 1080p, 720p, 480p, 360p / Mobile: 720p, 480p, 360p, 240p | Standard: 1080p, 720p, 480p, 360p |
| Segment length | 4 seconds / 6 seconds / 10 seconds | 6 seconds |

### Video - Extract audio  (`video-extract-audio`)

Save the sound of a video as MP3, M4A, FLAC, WMA, AC3.... Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Format | MP3 / M4A (AAC) / Opus / OGG Vorbis / FLAC (lossless) / WAV (uncompressed) / AAC (raw .aac) / WMA / AC3 (Dolby Digital) / MP2 / AIFF / M4R (iPhone ringtone) | MP3 |
| Bitrate _(when format = mp3/m4a/opus/ogg/aac/wma/ac3/mp2/m4r)_ | 128 kbps / 192 kbps / 256 kbps / 320 kbps | 192 kbps |

### Video - Make a GIF  (`video-gif`)

Turn a part of a video into an animated GIF. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Start at | text | 0 |
| Length | 0.5 to 120 s | 5 |
| Width | 64 to 1920 px | 480 |
| Frames per second | 1 to 30 fps | 12 |

### Video - Replace / mix audio  (`video-replace-audio`)

Put a different sound track on a video. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| New sound | a file (mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif) |  |
| How | Replace the original sound / Mix with the original sound | Replace the original sound |

### Video - Rotate / flip  (`video-rotate`)

Turn a sideways video upright or mirror it. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Transform | Rotate 90° clockwise / Rotate 90° counter-clockwise / Rotate 180° / Flip horizontally (mirror) / Flip vertically | Rotate 90° clockwise |
| Quality | Smaller file / Balanced / High quality | High quality |

### Video - Burn in subtitles  (`video-subtitles`)

Draw an .srt / .ass subtitle file onto the picture. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| Subtitle file | a file (srt, ass, ssa, vtt) |  |
| Text size | 8 to 72 pt | 24 |
| Quality | Smaller file / Balanced / High quality | High quality |

### Video - Save a frame as picture  (`video-frame`)

Grab a still image from a video. Accepts: mp4, m4v, mov, mkv, webm, avi, wmv, flv, mpg, mpeg, 3gp, ts, m2ts, ogv.

| Option | Choices / range | Default |
|---|---|---|
| At time | text | 0:01 |
| Picture format | PNG (lossless) / JPG (smaller) | PNG (lossless) |


## Audio (6 tools)

### Audio - Convert  (`audio-convert`)

Change format, bitrate, sample rate or channels. Accepts: mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif.

| Option | Choices / range | Default |
|---|---|---|
| Format | MP3 / M4A (AAC) / Opus / OGG Vorbis / FLAC (lossless) / WAV (uncompressed) / AAC (raw .aac) / WMA / AC3 (Dolby Digital) / MP2 / AIFF / M4R (iPhone ringtone) | MP3 |
| Bitrate _(when format = mp3/m4a/opus/ogg/aac/wma/ac3/mp2/m4r)_ | 128 kbps / 192 kbps / 256 kbps / 320 kbps | 192 kbps |
| Sample rate | Keep original / 44.1 kHz / 48 kHz | Keep original |
| Channels | Keep original / Mono / Stereo | Keep original |

### Audio - Trim  (`audio-trim`)

Cut a part out of an audio file. Accepts: mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif.

| Option | Choices / range | Default |
|---|---|---|
| Start | text | 0:00 |
| End | text |  |
| Cut mode | Fast - no re-encoding / Precise - re-encode (exact cut) | Fast - no re-encoding |

### Audio - Volume / normalize  (`audio-volume`)

Make quiet files louder, even out loudness. Accepts: mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif.

| Option | Choices / range | Default |
|---|---|---|
| What to do | Normalize loudness / Change volume (dB) | Normalize loudness |
| Target loudness _(when mode = normalize)_ | -16 LUFS - podcasts, YouTube, general / -14 LUFS - Spotify / streaming / -23 LUFS - broadcast (EBU R128) | -16 LUFS - podcasts, YouTube, general |
| Volume change _(when mode = gain)_ | -30 to 30 dB | 6 |

### Audio - Change speed  (`audio-speed`)

Faster or slower without changing the pitch. Accepts: mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif.

| Option | Choices / range | Default |
|---|---|---|
| Speed | 0.25 to 8 x | 1.5 |

### Audio - Join audio files  (`audio-merge`)

Put several recordings one after another. Accepts: mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif. Joins all selected files into ONE result (order = list order).

| Option | Choices / range | Default |
|---|---|---|
| Format | MP3 / M4A (AAC) / FLAC (lossless) / WAV | MP3 |
| Bitrate _(when format = mp3/m4a)_ | 128 kbps / 192 kbps / 256 kbps / 320 kbps | 192 kbps |
| Silence between files | 0 to 30 s | 0 |

### Audio - Fade in / out  (`audio-fade`)

Smooth start and end. Accepts: mp3, m4a, aac, wav, flac, ogg, oga, opus, wma, aiff, aif.

| Option | Choices / range | Default |
|---|---|---|
| Fade in | 0 to 60 s | 2 |
| Fade out | 0 to 60 s | 3 |


## Image (7 tools)

### Image - Convert / compress  (`image-convert`)

Change format, lower quality, limit the size. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

| Option | Choices / range | Default |
|---|---|---|
| Format | JPEG / PNG / WebP / AVIF / TIFF / BMP / GIF / ICO (icon, up to 256 px) / PDF (one page) / PSD (Photoshop) / TGA / JPEG 2000 | JPEG |
| Quality _(when format = jpg/webp/avif/jp2)_ | 1 to 100 % | 85 |
| Size | Keep original size / Longest side 3840 px (4K) / Longest side 2560 px / Longest side 1920 px (Full HD) / Longest side 1280 px / Longest side 1024 px / Longest side 800 px | Keep original size |
| Remove metadata (EXIF, GPS, camera info) | on / off | on |

### Image - Compress  (`image-compress`)

Make pictures smaller with a simple quality level. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

| Option | Choices / range | Default |
|---|---|---|
| Compression | Maximum quality (95) / High (85) - looks identical / Medium (70) - good for sharing / Small (50) / Tiny (30) - visible loss | Medium (70) - good for sharing |
| Format | Keep each file's format / Convert to JPEG / Convert to WebP | Keep each file's format |
| Size | Keep original size / Longest side 3840 px / Longest side 2560 px / Longest side 1920 px / Longest side 1280 px | Keep original size |
| Remove metadata (EXIF, GPS, camera info) | on / off | on |

### Image - Resize  (`image-resize`)

Scale by percent, width, height or to a box. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

| Option | Choices / range | Default |
|---|---|---|
| Resize | By percentage / By width (keep proportions) / By height (keep proportions) / Fit inside a box (keep proportions) / Fill a box (crops the overflow) / Exact size (may distort) | By percentage |
| Scale _(when mode = percent)_ | 1 to 800 % | 50 |
| Width _(when mode = width/fit/fill/exact)_ | 1 to 30000 px | 1920 |
| Height _(when mode = height/fit/fill/exact)_ | 1 to 30000 px | 1080 |
| Never enlarge _(when mode = width/height/fit)_ | on / off | on |
| Quality (JPEG / WebP / AVIF) | 1 to 100 % | 90 |

### Image - Resize to a preset  (`image-preset`)

Instagram, YouTube, X, Facebook, passport and other ready-made sizes. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

| Option | Choices / range | Default |
|---|---|---|
| Size | Instagram post - square 1080 x 1080 / Instagram post - portrait 1080 x 1350 / Story / Reel / TikTok 1080 x 1920 / YouTube thumbnail 1280 x 720 / X / Twitter post 1200 x 675 / Facebook cover 820 x 312 / LinkedIn banner 1584 x 396 / Full HD 1920 x 1080 / 4K 3840 x 2160 / Profile picture 400 x 400 / Passport photo 600 x 600 / App icon 512 x 512 | Instagram post - square 1080 x 1080 |
| How | Fill the frame (crop the edges) / Fit inside (add borders) | Fill the frame (crop the edges) |
| Borders _(when fit = pad)_ | White / Black / Transparent (PNG) / Blurred copy of the picture | White |

### Image - Crop / rotate  (`image-crop-rotate`)

Crop to a shape, rotate or flip. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

| Option | Choices / range | Default |
|---|---|---|
| Rotate | Don't rotate / 90° clockwise / 180° / 90° counter-clockwise | Don't rotate |
| Flip | No flip / Mirror left-right / Mirror top-bottom | No flip |
| Crop | Don't crop / Crop to a shape / Crop to exact pixels | Crop to a shape |
| Shape _(when crop = aspect)_ | Square 1:1 / 4:3 / 3:2 / 16:9 widescreen / 3:4 portrait / 2:3 portrait / 4:5 portrait / 9:16 vertical | Square 1:1 |
| Keep the _(when crop = aspect)_ | Centre / Top / Bottom / Left / Right | Centre |
| Left _(when crop = exact)_ | 0 to 100000 px | 0 |
| Top _(when crop = exact)_ | 0 to 100000 px | 0 |
| Width _(when crop = exact)_ | 1 to 100000 px | 1000 |
| Height _(when crop = exact)_ | 1 to 100000 px | 1000 |

### Image - Add a watermark  (`image-watermark`)

Stamp text or a logo on pictures. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

| Option | Choices / range | Default |
|---|---|---|
| Watermark | Text / Picture (logo) | Text |
| Text _(when kind = text)_ | text | © Your name |
| Logo picture _(when kind = image)_ | a file (jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg) |  |
| Position | Bottom right / Bottom left / Top right / Top left / Center | Bottom right |
| Size | Small / Medium / Large | Medium |
| Opacity | 90% / 70% / 50% / 30% | 70% |

### Image - Remove metadata  (`image-strip`)

Delete EXIF, GPS location and camera info. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg.

No options.


## PDF (12 tools)

### PDF - Merge  (`pdf-merge`)

Join several PDFs into one. Accepts: pdf. Joins all selected files into ONE result (order = list order).

No options.

### PDF - Extract / remove / split pages  (`pdf-pages`)

Keep, remove or split pages. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| What to do | Keep only these pages / Remove these pages / Split into one file per page / Split every N pages | Keep only these pages |
| Pages _(when mode = extract/remove)_ | text | 1 |
| Pages per file _(when mode = split_n)_ | 1 to 10000 | 10 |

### PDF - Pages to pictures  (`pdf-to-images`)

Save PDF pages as PNG or JPG. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Picture format | PNG (sharp, larger) / JPG (smaller) | PNG (sharp, larger) |
| Resolution | 72 dpi - small, for screens / 150 dpi - good for reading / 200 dpi / 300 dpi - for printing | 150 dpi - good for reading |
| Pages | text |  |

### PDF - Extract text  (`pdf-to-text`)

Save the text of a PDF as a .txt file. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Keep the page layout (columns, tables) | on / off | on |

### PDF - Rotate pages  (`pdf-rotate`)

Turn all or some pages. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Rotate | 90° clockwise / 180° / 90° counter-clockwise | 90° clockwise |
| Pages | text |  |

### PDF - Compress  (`pdf-compress`)

Shrink the pictures inside a PDF (scans, photos). Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Compression | Light - pictures stay sharp / Medium - good for e-mail / Strong - smallest, pictures get softer | Medium - good for e-mail |

### PDF - Optimize (lossless)  (`pdf-optimize`)

Reduce PDF size without losing quality. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Fast web view (linearize) | on / off | off |

### PDF - Add a text watermark  (`pdf-watermark`)

Stamp CONFIDENTIAL, DRAFT or your own text on every page. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Text | text | CONFIDENTIAL |
| Position | Diagonal across the page / Bottom of the page | Diagonal across the page |
| Size | Small / Medium / Large | Large |
| Strength | Strong (50%) / Medium (30%) / Faint (15%) | Medium (30%) |
| Color | Gray / Black / Light gray | Gray |

### PDF - Add a password  (`pdf-protect`)

Encrypt a PDF so it asks for a password. Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Password to open | typed secret (never saved) |  |
| Also forbid copying and editing | on / off | off |

### PDF - Remove the password  (`pdf-unprotect`)

Save an unlocked copy (you must know the password). Accepts: pdf.

| Option | Choices / range | Default |
|---|---|---|
| Current password | typed secret (never saved) |  |

### PDF - Remove document info  (`pdf-metadata`)

Delete author, title and creation info. Accepts: pdf.

No options.

### PDF - Pictures to PDF  (`image-to-pdf`)

Make one PDF from one or many pictures. Accepts: jpg, jpeg, png, webp, bmp, tif, tiff, gif, ico, heic, heif, avif, jp2, tga, psd, svg. Joins all selected files into ONE result (order = list order).

| Option | Choices / range | Default |
|---|---|---|
| Page size | A4 / US Letter / Same size as each picture | A4 |
| Orientation _(when page = a4/letter)_ | Automatic (per picture) / Portrait / Landscape | Automatic (per picture) |
| Margin _(when page = a4/letter)_ | None / Small / Medium | Small |
| Picture quality | High quality / Balanced / Smaller file | High quality |


## Documents (13 tools)

### Documents - PowerPoint to PDF  (`ppt-to-pdf`)

Convert slides (PPT, PPTX, ODP) to PDF. Accepts: ppt, pptx, pps, ppsx, odp.

No options.

### Documents - Word to PDF  (`word-to-pdf`)

Convert documents (DOC, DOCX, ODT, RTF, TXT) to PDF. Accepts: doc, docx, odt, rtf, txt, dot, dotx.

No options.

### Documents - Excel to PDF  (`excel-to-pdf`)

Convert spreadsheets (XLS, XLSX, ODS, CSV) to PDF. Accepts: xls, xlsx, ods, csv.

No options.

### Documents - PDF to Word  (`pdf-to-word`)

Make an editable .docx from a PDF. Accepts: pdf.

No options.

### Documents - PDF to PowerPoint  (`pdf-to-slides`)

Make an editable .pptx from a PDF. Accepts: pdf.

No options.

### Documents - PDF to Excel  (`pdf-to-sheet`)

Pull the text and tables of a PDF into an .xlsx. Accepts: pdf.

No options.

### Documents - Update old Office files  (`office-modernize`)

DOC to DOCX, XLS to XLSX, PPT to PPTX. Accepts: doc, dot, rtf, xls, xlt, ppt, pps.

No options.

### Documents - Office to OpenDocument  (`office-to-odf`)

DOCX/XLSX/PPTX to ODT/ODS/ODP. Accepts: doc, docx, rtf, xls, xlsx, ppt, pptx.

No options.

### Documents - OpenDocument to Office  (`odf-to-office`)

ODT/ODS/ODP to DOCX/XLSX/PPTX. Accepts: odt, ods, odp.

No options.

### Documents - Spreadsheet to CSV  (`sheet-to-csv`)

Save the first sheet of an Excel / ODS file as CSV. Accepts: xls, xlsx, ods, xlt.

| Option | Choices / range | Default |
|---|---|---|
| Separator | Comma ( , ) / Semicolon ( ; ) / Tab | Comma ( , ) |

### Documents - CSV to spreadsheet  (`csv-to-sheet`)

Open a CSV as a real Excel / ODS file. Accepts: csv.

| Option | Choices / range | Default |
|---|---|---|
| Separator in the CSV | Comma ( , ) / Semicolon ( ; ) / Tab | Comma ( , ) |
| Save as | Excel (.xlsx) / OpenDocument (.ods) | Excel (.xlsx) |

### Documents - Document to HTML  (`doc-to-html`)

Save a Word / ODT / RTF / TXT document as a web page. Accepts: doc, docx, odt, rtf, txt, dot, dotx.

No options.

### Documents - HTML to document  (`html-to-doc`)

Turn a web page file into .docx or .odt. Accepts: html, htm.

| Option | Choices / range | Default |
|---|---|---|
| Save as | Word (.docx) / OpenDocument (.odt) | Word (.docx) |

