# Privacy Policy - KinoFlux Editor 0.1.2

Effective for KinoFlux Editor version 0.1.2 and later. Publisher: ntxm.org (https://ntxm.org, contact@ntxm.org).

## In one paragraph

KinoFlux Editor works completely offline. It has no accounts, no telemetry, no analytics, no advertising,
no crash reporting service and no update checker. Your files are converted on your own computer by programs
that are installed with the app, and they are never uploaded anywhere. We (ntxm.org) do not receive, collect,
store or share any information about you or your files.

## What the app does NOT do

- It does not connect to the internet - not to process files, not to check for updates, not to send statistics.
- It does not ask you to sign in or create an account.
- It does not read your files except the ones you add to the list, and it never changes the originals: results
  are always written as new files.
- It does not collect your name, email address, location, device identifiers or usage statistics.
- It does not share anything with third parties, because it has nothing to share.

How we checked this is described in docs/DATA_HANDLING.md ("Network audit").

## What is stored on your computer

Everything below stays on your computer, inside your own user profile. You can look at it, copy it or delete it
at any time (see "Deleting your data").

| What | Where (Windows / macOS / Linux) | Content |
|------|----------------------------------|---------|
| Settings and presets | `%APPDATA%\KinoFlux Editor\settings.json` / `~/Library/Application Support/KinoFlux Editor/settings.json` / `~/.config/kinoflux-editor/settings.json` | theme, window size, last tool, recently used tools, how often each tool was used, last option values (never passwords or file paths), your saved presets, chosen output folder |
| Results history | `history.json` next to the settings | the last 200 finished jobs: tool name, input file name, output file path, size and time. Used only for the "Results" list. |
| Log files | `%LOCALAPPDATA%\KinoFlux Editor\logs` / `~/Library/Logs/KinoFlux Editor` / `~/.local/state/kinoflux-editor/logs` | start/stop, version, operating system, which tool ran, success or failure and the error text of the conversion program. Error text can contain file names. Rotated: at most about 4 MB. |
| Crash reports | `crash` folder inside the logs folder | written only if the app crashes: version, operating system, the error message and where it happened. Nothing is sent anywhere; send it to us only if you choose to. |
| Temporary files | the system temp folder | preview pictures for trimming, unfinished results (`.part`), LibreOffice scratch folders. Removed after use. |
| LibreOffice profile | `%LOCALAPPDATA%\KinoFlux Editor\cache\lo-profile` / `~/Library/Caches/KinoFlux Editor/lo-profile` / `~/.cache/kinoflux-editor/lo-profile` | the settings folder LibreOffice needs to convert documents. Contains no documents. |

Passwords you type for PDFs are used for that one job only. They are handed to the conversion program on its
command line while the job runs and are never written to the settings, the history or the logs.

## Files you process

Your files are opened by FFmpeg, ImageMagick, qpdf, Poppler and LibreOffice - programs that run on your
computer as separate processes. The app gives them only local file paths. Results are written next to the
originals or into the folder you choose.

## Links

The About window contains links to our website and e-mail address. They are opened by your web browser or mail
program only when you click them. What happens then is governed by the privacy policy of that website and program.

## Installer

The installer does not connect to the internet. It writes the program files, shortcuts and an uninstall entry
(and, only if you choose that option, the "Open with" menu entries). The uninstaller can optionally delete your
saved settings, history, presets and logs.

## Deleting your data

- Uninstall the app and tick "Remove my settings, presets, history and logs" in the uninstaller; or
- delete the folders listed in the table above; or
- inside the app: Results > Clear list removes the history; deleting a preset removes it from the settings.

## Children

The app is a general-purpose tool and collects no personal data from anyone, including children.

## Changes

If a future version ever adds a network feature, it will be off by default, clearly explained in the app, and
this policy will be updated before it ships.

## Contact

ntxm.org - contact@ntxm.org - https://ntxm.org
