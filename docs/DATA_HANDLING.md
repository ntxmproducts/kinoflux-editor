# Data handling statement - KinoFlux Editor 0.1.2

Short, technical version of the [Privacy Policy](../PRIVACY.md).

> The scripts and tests named below (`scripts/check-offline.ps1`, `cargo test -p vtd-session --test no_network`) belong to the private source code and are not part of this repository.

## Data flow

```
 you pick files  ->  KinoFlux Editor (local process)  ->  FFmpeg / ImageMagick / qpdf / Poppler / LibreOffice
                                                            (local child processes, local file paths only)
                                                       ->  new files next to the originals or in your chosen folder
```

There is no server side. Nothing leaves your computer.

## Inventory of stored data

See the table in the Privacy Policy. Summary: settings + presets + history (JSON, per user), rotating log
files, crash reports (only after a crash), temporary files (deleted after the job), LibreOffice profile (cache).
No document content, no file content and no passwords are stored.

## Retention

- Settings, presets: until you delete them.
- History: the newest 200 entries; "Clear list" empties it.
- Logs: rotated, three old files of at most 1 MB are kept next to the current one. Crash reports: the newest 10 are kept.
- Temporary files: removed when the job finishes or is cancelled (an abnormal exit can leave some in the temp folder, which the operating system cleans).

## Network audit (how "no network" was verified)

Performed for version 0.1.2 on 2026-10-03 and repeatable with `scripts/check-offline.ps1` and
`cargo test -p vtd-session --test no_network` (the test also scans our own sources for sockets and URLs).

1. **Dependency audit.** `cargo tree` for the Windows, macOS (Intel and Apple Silicon) and Linux targets contains
   no HTTP client, TLS library or networking stack: no `reqwest`, `hyper`, `ureq`, `rustls`, `native-tls`, `openssl`, `schannel`,
   `curl`, `tokio`. The only networking-related crates present are `gpui-pre-http-client` (a trait that GPUI
   declares for loading remote images; no implementation is linked), `async-net` (socket helpers used by the GPUI
   executor), and on Linux `zbus` / `ashpd` / `oo7` (local D-Bus desktop portals for file dialogs). The code of
   KinoFlux Editor itself uses no sockets, no HTTP and no URL loading. (`gpui-pre-reqwest` appears only for the
   WebAssembly target of `gpui-kit-assets`, which is not built.)
2. **Binary audit.** The Windows executable imports only Windows system libraries for windows, graphics (Direct3D 11,
   DirectWrite, DXGI), input, accessibility (UI Automation) and the C runtime. It does not import `winhttp.dll`,
   `wininet.dll`, `urlmon.dll` or any TLS/crypto-protocol library (`scripts/check-offline.ps1` prints the full
   import list and fails if one of these appears).
3. **Runtime audit.** `scripts/check-offline.ps1` starts the application, runs a real conversion (`--tool image-convert
   --start`) and samples every TCP and UDP endpoint of the application and its child programs for 10 seconds. Result
   for 0.1.2 (2026-10-03, Windows 11): no endpoint was opened; two processes were seen (the application and ImageMagick),
   and the converted file was produced. It is a spot check, not a proof; the guarantees come from items 1 and 4.
4. **Bundled programs.** FFmpeg and Poppler are built with network protocol support (FFmpeg: HTTP, SRT, SSH, ...;
   Poppler: libcurl), and LibreOffice has an update checker in its interactive mode. KinoFlux Editor passes them
   only existing local files (paths picked in the file list; typed paths in options are verified to exist) and starts
   LibreOffice headless with a private profile, so none of these features is reachable from the app. This is a design
   guarantee of the command lines, not an operating-system sandbox; if you need a hard guarantee, block the
   installation folder in your firewall.

## Third parties

No data processors, no sub-processors, no cloud services.

## Security notes

- Programs are started with argument lists, never through a shell, so file names cannot inject commands.
- PDF passwords are visible on the command line of the qpdf process while that job runs (other programs running as the same user could see them).
- The Windows installer is not code-signed in version 0.1.2 (SmartScreen may warn); see the README.
