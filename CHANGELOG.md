# Changelog

All notable changes to Arc Flow are documented here, newest first. This file
tracks high-level release history; each version's full release notes
(including any known issues) are also published on the
[Releases](../../releases) page alongside the downloadable installers.

This project does not follow semantic versioning strictly pre-1.0 — version
numbers increase with each release, but a minor-version bump does not always
imply a breaking change, since there is no public API surface to break.

## [Unreleased]

- Nothing yet.

## [0.2.3]

- Added a global Snippets On/Off switch. Snippets stay saved while paused.
- Added Smart and Always insertion modes. Smart snippets use sentence context;
  Always snippets keep classic macro behavior.
- Improved exact insertion for links, addresses, signatures, repeated triggers,
  and overlapping trigger phrases.
- Added Hinglish (Roman script) transcription and explicitly disabled unwanted
  Whisper translation.
- Lists now stay in sentence form unless the speaker asks for a list or counts
  out the items.
- Added 25 time-aware Home greetings that remain stable while navigating and
  update when the time of day changes.
- Improved dictation-island visibility, stale-timer handling, and recovery.
- Failed text insertion now offers a copy action instead of showing a false
  success message.
- Added a Home notice while global hotkeys are paused.
- Updated the public support contact details.

## [0.2.2]

- Improved reliability of the dictation overlay, including automatic
  recovery if its display process becomes unresponsive.
- Update installation no longer briefly shows a console window during the
  restart step.
- Added in-app release notes, and forms for sending feedback, reporting
  bugs, and requesting features directly from the app.
- Added optional crash reporting (off by default, and only sent if you
  choose to send a specific report).
- Clarified the hold-duration guidance for the Ctrl+Win hotkey in the
  onboarding guide.

---

Older versions were not tracked in this changelog format; see the
[Releases](../../releases) page for the complete history.
