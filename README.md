# Arc Flow

Arc Flow is a privacy-first voice dictation app for Windows. Press a hotkey,
speak, and your words are transcribed and typed directly into whatever
you're working in — with on-device speech-to-text by default, so your voice
never has to leave your computer.

This repository is the **public release and support hub** for Arc Flow. It
is used for downloads, documentation, bug reports, and feature requests.

> **This repository does not contain Arc Flow's source code.**
> Arc Flow is proprietary software — free to use, but closed source. The
> application's implementation lives in a private repository and is not
> published here or anywhere else. See [LICENSE](LICENSE) for the full
> terms.

## Table of contents

- [Download](#download)
- [Reporting a bug](#reporting-a-bug)
- [Requesting a feature](#requesting-a-feature)
- [Including logs and screenshots safely](#including-logs-and-screenshots-safely)
- [Support](#support)
- [Security](#security)
- [Changelog](#changelog)
- [License](#license)

## Download

The latest installer (MSI) and portable build (ZIP) are published on the
[Releases](../../releases) page of this repository, along with SHA256
checksums for every file. Always verify the checksum before running an
installer you've downloaded, especially from a mirror.

Builds are also available from the Arc Flow website (linked in this
repository's "About" section, top right of this page).

## Reporting a bug

Found something broken? Please [open a bug report](../../issues/new?template=bug_report.yml).
The form will ask for your app version, OS version, installation type, and
steps to reproduce — that's the information that helps us fix it fastest.

If the app crashed outright, use the
[crash report template](../../issues/new?template=crash_report.yml) instead
— it asks for a few crash-specific details (what you were doing, the error
message, and the crash log) that a regular bug report doesn't.

## Requesting a feature

Have an idea or a workflow Arc Flow doesn't support yet? Open a
[feature request](../../issues/new?template=feature_request.yml). Tell us
the problem you're trying to solve, not just the solution you have in
mind — it helps us design something that fits well with the rest of the app.

## Including logs and screenshots safely

Logs and screenshots are genuinely helpful, but please check them before
attaching:

- **Redact API keys or tokens** if a log line ever shows one (Arc Flow's own
  logs shouldn't print keys, but double-check custom-endpoint configs).
- **Don't paste dictated audio transcripts or note content** if it's
  personal or sensitive — a description of what happened is usually enough.
- **Crop screenshots** to the relevant window/dialog rather than your full
  desktop, if your desktop has personal information visible.
- Arc Flow's log file can be found via **Settings → Help → Open Log
  Folder** in the app.

## Support

For general "how do I…" questions, see [SUPPORT.md](SUPPORT.md). For bugs
and feature requests, use the issue templates above. For anything
sensitive — security reports, account or licensing issues, accidental
exposure of private data — do **not** open a public issue; see
[SECURITY.md](SECURITY.md) instead.

## Security

Please report vulnerabilities and other sensitive issues privately rather
than through a public GitHub issue. Full instructions are in
[SECURITY.md](SECURITY.md).

## Changelog

Release-by-release history of what's shipped is in
[CHANGELOG.md](CHANGELOG.md), and every release on the
[Releases](../../releases) page includes its own detailed notes.

## License

Arc Flow is free to use, but it is **proprietary, closed-source software**.
This repository contains no application source code — only documentation,
issue templates, and release artifacts. See [LICENSE](LICENSE) for the full
terms governing your use of the compiled application.
