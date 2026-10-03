# Security policy

## Supported versions

Security fixes go into the latest release of KinoFlux Editor. At the moment that is **0.1.2**.

| Version | Supported |
|:--------|:---------:|
| 0.1.2 | Yes |
| Earlier (Tauri-based) releases | No |

## Reporting a vulnerability

Please **do not open a public issue** for a security problem.

Email **[contact@ntxm.org](mailto:contact@ntxm.org)** with:

- what you found and the version of KinoFlux Editor (About window, <kbd>F1</kbd>),
- your operating system (Windows 10/11 or macOS version),
- steps to reproduce it, and the impact you think it has.

Do not attach private or confidential files. If a file is needed to reproduce the problem, describe it or make a harmless sample.

You can expect an acknowledgement and a plain reply on whether we can reproduce it. Please give us reasonable time to fix a problem before you publish details.

## Good to know

- KinoFlux Editor has **no network code**, no accounts and no update check. See [PRIVACY.md](PRIVACY.md) and [docs/DATA_HANDLING.md](docs/DATA_HANDLING.md).
- Check your download against the SHA-256 values in the [README](README.md#download) or on the [release page](https://github.com/ntxmproducts/kinoflux-editor/releases/tag/v0.1.2). Only download the app from this repository or from [ntxm.org](https://ntxm.org).
- The Windows installer is not code-signed and the macOS app is not notarized yet, so the operating system will warn you on first start. That is expected for these builds.
- PDF passwords are handed to `qpdf` on its command line for the duration of one job, so other programs running as the same user could see them during that time. They are never saved. This is documented in the [known limitations](README.md#known-limitations).
