# Third-party notices

> The `licenses` folder mentioned below ships inside the installer and the app (and in About > Third-party notices). This repository only carries this page.

KinoFlux Editor is (c) 2026 ntxm.org and is licensed under the KinoFlux Editor Proprietary License (see the
Licence page). It is built from, and ships with, third-party software. That software stays under its own licence;
nothing in the KinoFlux Editor licence restricts the rights those licences give you. This page lists what is
included, under which licence, and where the source code is.

The full licence texts are in the `licenses` folder next to the program (install folder, or the portable folder)
and in the `licenses` folder of the source repository: `GPL-3.0.txt`, `Apache-2.0.txt`, `ImageMagick-License.txt`,
`LGPL-2.1.txt`, `MPL-2.0.txt`, `LUCIDE-ICONS.txt` and `rust-crates.md` (every Rust library, with its licence
text). LibreOffice ships its own licence files inside its folder (`LICENSE.html`, `license.txt`, `NOTICE`).

## 1. Programs that run next to KinoFlux Editor

KinoFlux Editor does not contain the code of these programs. It starts them as separate programs
(command-line processes) with local file paths, and shows you their result. They are unmodified builds from the
projects named below.

| Program | Version | Used for | Licence | Source code and project |
|---|---|---|---|---|
| FFmpeg (ffmpeg.exe) | 8.0 "essentials" build by gyan.dev | all video and audio tools | **GNU GPL version 3 or later** (this build is compiled with `--enable-gpl --enable-version3`) | https://ffmpeg.org/releases/ffmpeg-8.0.tar.xz, build details https://www.gyan.dev/ffmpeg/builds/ |
| ImageMagick (magick.exe) | 7.1.2-11 Q16 x64 | all image tools | ImageMagick License (Apache-2.0 style) | https://imagemagick.org/, https://github.com/ImageMagick/ImageMagick |
| qpdf (qpdf.exe, qpdf30.dll, zlib-flate.exe, fix-qdf.exe) | 12.2.0 | PDF merge, split, protect, repair | Apache License 2.0 | https://github.com/qpdf/qpdf |
| Poppler (pdftoppm, pdftotext, pdfinfo and their libraries) | 26.09.0 (Windows build) | PDF to pictures, PDF to text | **GNU GPL version 2 or later** (used here under version 3) | https://poppler.freedesktop.org/, https://gitlab.freedesktop.org/poppler/poppler |
| LibreOffice (Portable) | 26.2.1.2 | Word, Excel, PowerPoint and other document conversion (only in the full package) | Mozilla Public License 2.0 and LGPL-3.0-or-later (plus the licences of the libraries inside it, see its LICENSE.html) | https://www.libreoffice.org/, https://git.libreoffice.org/core ; the portable packaging is by PortableApps.com (GPL-2.0 launcher) |

### 1.1 FFmpeg is a GPL build - what that means for you

* The FFmpeg build included here contains GPL-licensed encoders (x264, x265, Xvid, VidStab, Rubber Band and
  others). That makes the *FFmpeg program* GPL version 3. KinoFlux Editor only runs it as a separate program, so
  KinoFlux Editor itself stays under its own licence, but you must be able to get the FFmpeg source code and you
  keep all the rights the GPL gives you for FFmpeg (use, study, change, share). The GPL text is in
  `licenses/GPL-3.0.txt`.
* **Written offer for the source code (GPL section 6):** for at least three years from the day you received
  KinoFlux Editor, ntxm.org will send you, on request and for no more than the cost of copying, the complete
  corresponding source code of the GPL-licensed programs in this package (FFmpeg and Poppler) in the exact version
  shipped. Write to **contact@ntxm.org**. The unmodified upstream sources are also public (links above); the
  build recipe of the FFmpeg binary is the `configuration:` line printed by `ffmpeg -version` and the gyan.dev
  build page.
* The GPL libraries inside the FFmpeg build have their own sources: x264 https://code.videolan.org/videolan/x264,
  x265 https://bitbucket.org/multicoreware/x265_git, Xvid https://www.xvid.com/, libvidstab
  https://github.com/georgmartius/vid.stab, Rubber Band https://breakfastquay.com/rubberband/. Other libraries in
  that build (libaom, libvpx, Opus, Vorbis, LAME, Theora, libwebp, OpenJPEG, libass,
  FreeType, FriBidi, HarfBuzz, zimg, libvmaf, GnuTLS, libxml2 and more) are under BSD, MIT, LGPL or similar licences.
* **Patents.** Video and audio formats such as H.264, H.265/HEVC and AAC can be covered by patents in some
  countries. Open-source licences, including the GPL, do not grant patent licences for them. If you use KinoFlux
  Editor commercially in a way that needs such a licence, getting it is your responsibility.
* **Network code inside FFmpeg.** This FFmpeg build can open network addresses (SRT, SSH, ZeroMQ, HTTPS through
  GnuTLS). KinoFlux Editor never gives it an address: every input is a file path you picked, checked to be an
  existing local file. See the Data handling page.

### 1.2 Poppler and its libraries

The Poppler package contains the utilities `pdftoppm`, `pdftotext` and `pdfinfo` (the other utilities in the
Windows build are not used) and the libraries they need: cairo (LGPL-2.1 / MPL-1.1), FreeType (FreeType License
or GPL-2.0), HarfBuzz, fontconfig, glib/gobject/gio (LGPL-2.1+), libpng, libjpeg-turbo, libtiff, OpenJPEG, LittleCMS,
pixman, zlib, zstd, liblzma, bzip2, expat, PCRE2, ICU (Unicode License), libffi, libiconv, gettext's libintl
(LGPL), libcurl (curl licence), libssh2, OpenSSL 3 (Apache-2.0), MIT Kerberos (BSD-style) and the Microsoft Visual
C++ runtime DLLs (redistributable under the Microsoft Visual Studio redistribution terms). The Poppler
programs are run only on local files; libcurl and OpenSSL are present because the upstream Windows build links
them, they are not given any address by KinoFlux Editor.

### 1.3 LibreOffice

LibreOffice is started in the background (headless, with its own throw-away profile folder under your cache
folder) to convert documents. It is licensed under the Mozilla Public License 2.0 / LGPL-3.0-or-later. The source
code is available at https://git.libreoffice.org/core and from The Document Foundation. LibreOffice and the
LibreOffice logo are trademarks of The Document Foundation; KinoFlux Editor is not affiliated with or endorsed by
The Document Foundation, FFmpeg, ImageMagick Studio, qpdf, or the Poppler project.

### 1.4 The macOS package (Apple Silicon)

The macOS app carries its own copies of the programs above, inside `KinoFlux Editor.app/Contents/Resources/binaries`
(licence texts and the exact versions: `Contents/Resources/licenses/macos-helper-programs/`, list in
`BUNDLED-VERSIONS.txt`):

* **FFmpeg / ffprobe 8.0** - a static **GPL** build (x264, x265, libvpx, aom, SVT-AV1, LAME, Opus, Vorbis, Theora, libwebp, libass,
  OpenJPEG; Apple VideoToolbox) from https://www.osxexperts.net/, source https://ffmpeg.org/releases/ffmpeg-8.0.tar.xz. GPL-2.0-or-later
  (the build line is printed by `ffmpeg -version`); the rest of section 1.1 applies unchanged.
* **ImageMagick 7.1.2** (ImageMagick licence, Apache-2.0 style), **qpdf 12.4.2** (Apache-2.0), **Poppler 26.09** (GPL-2.0 or 3.0)
  - Homebrew builds, with the libraries they need as separate, replaceable `.dylib` files in `binaries/lib`: libheif 1.23 and
  libde265 (LGPL-3.0), glib, gpgme and libgpg-error (LGPL-2.1+), Little CMS, FreeType (FTL), fontconfig, HarfBuzz, libpng, libtiff,
  libjpeg-turbo, libwebp, OpenJPEG, aom (BSD-2), x265 (GPL-2.0+), OpenSSL 3 (Apache-2.0), PCRE2, zstd, xz, and NSS / NSPR (MPL-2.0).
  The JPEG 2000 coder of ImageMagick is compiled from the ImageMagick source (same licence).
* Source code of every Homebrew component: the formula pages on https://formulae.brew.sh/ link the upstream tarballs; the same
  written offer as in section 1.1 applies (contact below) for the GPL parts, valid for three years after the release.
* **LibreOffice is not part of the macOS package**; install it yourself (section 1.3). KinoFlux Editor only starts it.

## 2. Rust libraries built into the program

KinoFlux Editor is written in Rust. These libraries (about 640 crate versions, resolved for the Windows, macOS and
Linux builds) are compiled into the executable. All are under permissive or weak-copyleft licences, summarised
here; each library's full licence text is in `licenses/rust-crates.md`:

| Licence | Libraries |
|---|---|
| Apache License 2.0 | 467 |
| MIT License | 150 |
| Unicode License v3 | 19 |
| BSD 3-Clause "New" or "Revised" License | 9 |
| Creative Commons Zero v1.0 Universal | 3 |
| ISC License | 3 |
| zlib License | 3 |
| BSD Zero Clause License | 2 |
| Mozilla Public License 2.0 | 2 |
| BSD 2-Clause "Simplified" License | 1 |
| bzip2 and libbzip2 License v1.0.6 | 1 |

Notable parts: GPUI and gpui-component (the user-interface toolkit, Apache-2.0), gpui-kit, lopdf (PDF
rewriting), resvg/usvg/tiny-skia (SVG drawing), image and related decoders (thumbnails), serde and serde_json
(settings files), notify and the small platform crates (`windows`, `windows-sys` and others, MIT or Apache-2.0).
Two crates are under the Mozilla Public License 2.0 (file-level copyleft: their own source files stay open, which
they are; nothing else is affected). No Rust library in the program is under the GPL or LGPL.

## 3. Icons and fonts

* The small interface icons are from **Lucide** (ISC licence, some derived from Feather under the MIT licence);
  `licenses/LUCIDE-ICONS.txt`.
* The application icon and logo are (c) ntxm.org (brand artwork carried over from the earlier KinoFlux Editor
  desktop app) and are covered by the KinoFlux Editor licence, not by an open-source licence.
* No fonts are bundled; the program uses the fonts of your system.

## 4. Build and installer tools

The Windows installer is made with **Inno Setup** (Jordan Russell and Martijn Laan, Inno Setup License; installers
it builds may be distributed freely; https://jrsoftware.org/isinfo.php). The Inno Setup authors ask commercial users
of the compiler to buy a licence (not strictly required; https://jrsoftware.org/isorder.php) - the publisher decides. The
macOS and Linux packages are made with standard system tools. These tools are not part of what you run.

## 5. Notes and assumptions (for the publisher)

* The bundled program versions and licences above were read from the programs themselves (`-version` output) and
  from the projects' public pages on 2026-10-03; they are not a legal opinion. Review them with a lawyer before
  commercial distribution, in particular the GPL source-offer wording and the patent note.
* If you replace a bundled program, update this page, the `licenses` folder and `docs/BINARIES.md`.
* The Rust list is generated: `cargo about generate about.hbs -o licenses/rust-crates.md` (see `about.toml`).
