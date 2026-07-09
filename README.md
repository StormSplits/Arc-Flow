# Arc Flow

Privacy-first voice dictation for Windows. Press a hotkey, speak, and Arc
Flow types clean, punctuated text into whatever app you're using — your
browser, editor, chat, email, or IDE. Everything can run 100% on-device:
your voice and text never leave your machine unless you explicitly choose a
cloud provider.

Arc Flow is free to use, and free forever. It is not open-source — see
[LICENSE](LICENSE) — but there is no paywall, subscription, or account
requirement for the app itself.

This repository is the **public release and support hub** for Arc Flow. It
is used for downloads, documentation, bug reports, and feature requests.

> **This repository does not contain Arc Flow's source code.**
> Arc Flow is proprietary software — free to use, but closed source. The
> application's implementation lives in a private repository and is not
> published here or anywhere else. See [LICENSE](LICENSE) for the full
> terms.

## Table of contents

- [What it does](#what-it-does)
- [Privacy model](#privacy-model)
- [Using Arc Flow](#using-arc-flow)
- [Features](#features)
- [Download](#download)
- [Reporting a bug](#reporting-a-bug)
- [Requesting a feature](#requesting-a-feature)
- [Including logs and screenshots safely](#including-logs-and-screenshots-safely)
- [Support](#support)
- [Security](#security)
- [Privacy policy](#privacy-policy)
- [Changelog](#changelog)
- [License](#license)

## What it does

Arc Flow is a desktop dictation tool built to be **local-first**. A global
hotkey starts a dictation session; a small floating overlay shows that it's
listening; your speech is transcribed by an on-device Whisper model,
cleaned up and punctuated by a local LLM (or your chosen cloud model), and
then typed into the focused text field of whatever application you're in.

It works **system-wide** — anywhere a keyboard can type — by detecting the
focused window and inserting text via the Windows clipboard or simulated
keystrokes.

## Privacy model

The Local/Cloud choice you make during onboarding drives a runtime routing
policy. The active mode is always visible (a badge on the overlay names the
active provider whenever cloud processing is in use).

| Mode | Speech-to-text | Text cleanup / transforms | Data leaves device? |
|------|----------------|---------------------------|---------------------|
| **Local** (default) | On-device (Whisper / Parakeet) | On-device (bundled llama.cpp or Ollama) | **Never** |
| **Cloud** | Your chosen provider (Deepgram, ElevenLabs, Mistral, OpenAI, Groq, custom) | Your chosen provider (OpenAI, Anthropic, Gemini, Groq, DeepSeek, custom) | Only to **your** provider, using **your** API key |

Cloud API keys are stored locally (Windows Credential Manager) and are sent
only to the provider you pick — never to any Arc Flow server. Local mode is
fully functional offline after the one-time model download.

Arc Flow also talks to a small optional backend of ours for update checks,
in-app notices, and (only if you choose to use them) feedback/bug-report
forms and opt-in crash reporting — never for your dictation content. Full
details: [PRIVACY_POLICY.md](PRIVACY_POLICY.md).

## Using Arc Flow

A plain-English walkthrough for anyone who just downloaded the app — no
code required.

### 1. Install and first launch

Download the installer, run it, and open Arc Flow. The first time it
opens, a short setup wizard walks you through 6 steps:

1. **Welcome**
2. **Permissions** — a quick check that Arc Flow can access your microphone
3. **Speech-to-text** — pick On-Device (works offline, private) or a Cloud
   provider
4. **Text cleanup** — pick On-Device, Ollama, or a Cloud provider for
   punctuation/grammar cleanup and Command Mode (you can skip this — your
   words still get typed, just without AI cleanup)
5. **Shortcut** — confirm your dictation hotkey and pick a microphone if
   you have more than one
6. **Done**

Right after setup finishes, a one-time guide appears explaining every
hotkey and the app's main sections — it only shows once, but everything in
it is repeated below.

### 2. Hotkeys — what each one does

| Hotkey | What happens |
|---|---|
| `Ctrl + Space` (default, changeable) | Press once to **start** dictating from anywhere. Press again to **stop** — your cleaned-up words are typed into whatever field is focused. |
| `Ctrl + D` (default, changeable) | **Command Mode.** Select some text first, then press this and speak an instruction ("make this more formal," "summarize this"). The selection is rewritten in place. |
| `Ctrl + Q` (default, changeable) | **Notes Mode.** Speak from anywhere with nothing selected — it's saved as a new note with an auto-generated title, no typing into another app. |
| `Ctrl + Win` (fixed) | **Pause/resume all hotkeys.** Press and hold both keys together for about a second to turn every hotkey above off or on — handy while gaming or in a full-screen app. A quick tap alone won't trigger it. |

All three configurable hotkeys can be changed any time in **Settings →
Hotkeys**, including binding a mouse side-button instead of a keyboard
combo.

### 3. Where things are

| Section | What it's for |
|---|---|
| **Home** | Your dictation history, streaks, and stats |
| **Dictionary** | Teach Arc Flow words/names it keeps mishearing |
| **Snippets** | A spoken trigger phrase that expands into fixed text (a signature, a canned reply) |
| **Style** | Tone presets (Formal/Casual/Very Casual) per context (personal, work, email), and how aggressively cleanup rewrites your words |
| **Notes** | Everything you've dictated with the Notes hotkey, plus a normal rich-text editor |
| **Settings** | Hotkeys, microphone, AI Mode, Speech-to-Text, Privacy, Appearance, Advanced |
| **Help** | This same walkthrough, plus Send Feedback / Report a Bug / Suggest a Feature |

### 4. Updates

Arc Flow checks for updates in the background. When one's available, a
small download icon lights up next to the notification bell — click it to
see what's new before installing. Occasionally a release is marked as
required (a security or data-safety fix); those show a full-screen prompt
instead of the small icon. Either way, your models, snippets, dictionary,
history, and settings are always preserved across an update.

### 5. Feedback and bugs

**Help → Send Feedback / Report a Bug / Suggest a Feature** send directly
to us — nothing is sent unless you press Send. Crash reports are separate:
off by default (**Settings → Privacy**), and even when on, a crash is only
ever saved to a local file for you to review — sending one to us is a
separate, explicit action. You're also welcome to use this repository's
[issue templates](#reporting-a-bug) instead of, or in addition to, the
in-app forms.

## Features

- **Real-time dictation** into any application via a configurable global
  hotkey (default `Ctrl + Space`; `Ctrl + Win` pauses/resumes all hotkeys).
- **Command Mode** (`Ctrl + D`) — select text in any app, speak an
  instruction ("make this more formal", "summarize this", "translate to
  Hindi"), and Arc Flow replaces the selection with the transformed result.
- **Notes Mode** (`Ctrl + Q`) — speak a note from anywhere; it's saved with
  an auto-generated title.
- **Automatic cleanup** — filler-word removal ("um", "uh"), punctuation,
  capitalization, and spoken self-corrections ("no, make that five").
- **Writing styles** — per-context tone presets (formal / casual / very
  casual) for personal messages, work messages, email, etc.
- **Personal dictionary** — teach Arc Flow your names, jargon, and product
  terms.
- **Snippets** — voice-triggered text expansions for signatures, links, and
  canned responses.
- **Local notes** — a built-in 2-pane notes editor.
- **History & stats** — a searchable log of past dictations with
  word/session counts.
- **Cloud providers, your choice** — OpenAI, Anthropic, Google (Gemini),
  Groq, DeepSeek, or any custom OpenAI-compatible endpoint for cleanup;
  Deepgram, ElevenLabs, Mistral, OpenAI, or Groq for cloud speech-to-text —
  all using your own API key.
- **In-app notifications and release notes** — see what's new without
  leaving the app.
- **Self-updating** — optional updates show a small icon with what's-new
  notes; required updates show a clear full-screen prompt. Your local data
  always survives an update.
- **Feedback built in** — Send Feedback, Report a Bug, and Suggest a
  Feature forms right in the Help page; opt-in local crash reports you can
  review before choosing to send.
- **Hardware-aware** — detects NVIDIA (CUDA), AMD/Intel (Vulkan), or
  CPU-only and recommends an appropriate model and backend.
- **System tray** — runs quietly in the background; the hotkey works even
  when the window is hidden.

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

## Privacy policy

The complete, plain-language breakdown of what stays on your device, what
only goes to a cloud provider you chose, and the short list of things our
own backend ever sees, is in [PRIVACY_POLICY.md](PRIVACY_POLICY.md).

## Changelog

Release-by-release history of what's shipped is in
[CHANGELOG.md](CHANGELOG.md), and every release on the
[Releases](../../releases) page includes its own detailed notes.

## License

Arc Flow is free to use, but it is **proprietary, closed-source software**.
This repository contains no application source code — only documentation,
issue templates, and release artifacts. See [LICENSE](LICENSE) for the full
terms governing your use of the compiled application.
