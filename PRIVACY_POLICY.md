# Arc Flow Privacy Policy

**Effective date: July 9, 2026**

Arc Flow is a voice dictation app. This document explains, in plain language,
exactly what happens to your voice and your text — what stays on your
computer, what only ever goes to a service *you* chose and *you* control,
and what (very little) ever reaches us.

If you only read one section, read this one.

## The short version

- **Arc Flow has no accounts, no sign-in, and no login.** We don't know who
  you are.
- **On-device mode (the default): your voice and text never leave your
  computer.** Not to us, not to anyone.
- **Cloud mode (optional, your choice): your audio/text goes directly from
  your computer to the AI provider you picked** (OpenAI, Anthropic, Google,
  Groq, DeepSeek, or a custom endpoint), using your own API key. It does
  **not** pass through our servers on the way.
- **We never see your dictated words, your notes, your dictionary, or your
  API keys — under any mode.**
- The only things Arc Flow ever sends to our own servers are: a version
  check (to tell you about updates), a request for any in-app notices, and
  — only if you take a deliberate action — a bug report, feedback, a
  feature idea, or a crash report you chose to send.

The rest of this document goes through each of these in detail.

---

## 1. On-device (local) mode — nothing leaves your computer

When you use Arc Flow with on-device speech-to-text (Whisper or Parakeet)
and on-device text cleanup (the bundled local model or your own Ollama),
the entire pipeline runs on your machine:

- Your microphone audio is captured, transcribed, cleaned up, and typed into
  your active window — all locally.
- The audio itself is never written to disk and never saved anywhere. Only
  the final cleaned-up *text* is kept, and only in your local history,
  which lives entirely on your own computer.
- No network request of any kind is made to process your dictation in this
  mode.

This is the default mode, and it is fully functional offline once your
chosen model has been downloaded.

## 2. Cloud mode — data goes to the provider you chose, not to us

Arc Flow lets you optionally connect a cloud speech-to-text provider and/or
a cloud text-cleanup provider, using **your own account and your own API
key**. Today, that list is:

- **Cloud speech-to-text**: Deepgram, ElevenLabs, Mistral, OpenAI, Groq, or
  any custom OpenAI-compatible endpoint you configure.
- **Cloud text cleanup / Command Mode**: OpenAI, Anthropic, Google
  (Gemini), Groq, DeepSeek, or a custom OpenAI-compatible endpoint.

If you turn on cloud mode, your audio and/or transcript is sent **directly
from your device to that provider's servers** — not through any server we
operate. Your API key is sent along with it, exactly the way it would be if
you called that provider's API yourself, because that is, functionally,
what Arc Flow is doing on your behalf.

**We do not see, store, log, or have any access to that data.** It never
touches our infrastructure. Once it leaves your device, what happens to it
is governed entirely by that provider's own privacy policy and terms —
not this one, and not something we control. We are not responsible for how
a third-party AI provider handles data you choose to send it; that is the
trade-off of choosing cloud mode over on-device mode, and it's why Arc Flow
always shows you which mode is active.

If you'd rather nothing ever leaves your device, don't configure a cloud
provider — on-device mode is the default and is a complete experience on
its own.

## 3. Your API keys

If you add a cloud provider's API key, it is stored only in your operating
system's own secure credential store (Windows Credential Manager). It is
never written to Arc Flow's local database, never logged, and never sent
anywhere except directly to the provider it belongs to, when you use that
provider.

## 4. What's stored locally on your device

Your dictation history, personal dictionary, snippets, writing-style
preferences, notes, and settings are stored in a local database on your own
computer, encrypted at rest (SQLCipher, AES-256). The encryption key lives
only in your operating system's credential store. We have no copy of this
database, no access to it, and no way to read it remotely — it never leaves
your computer at all.

You can clear your dictation history at any time from **Settings →
Privacy**.

## 5. What Arc Flow's own servers actually do

Arc Flow talks to a small backend we operate (for checking updates and a
few optional, user-initiated features). Here is the complete list of what
that backend is used for — there is nothing beyond what's listed here:

| Feature | What's sent | Automatic, or only if you act? |
|---|---|---|
| Update check | The app version you're running | Automatic (a small periodic check, roughly hourly) |
| Release notes | Nothing personal — just fetches the notes for a version | Only when you open "what's new" |
| In-app notifications | Nothing personal — just the app version, to filter which notices apply | Automatic (periodic, cosmetic only) |
| Send Feedback / Report a Bug / Suggest a Feature | Whatever you type into that form, plus an optional email address if you choose to add one | **Only when you press Send** — never automatic |
| Crash reports | A local crash report you're shown *before* it's sent — app version, timestamp, and the code location/message of the crash. **Never your audio or dictated text.** | **Off by default, and only sent when you press Send on a specific report** |

None of this requires or creates an account. We don't assign you an ID, we
don't track you across sessions, and we don't run any analytics or
advertising tracking in the app.

If any of these backend calls fail (for example, you're offline), Arc Flow
simply treats it as "nothing new" — it never blocks or interferes with
dictation, which works fully offline regardless.

## 6. What we never collect, under any mode

- Your dictated audio or transcripts (unless you separately, explicitly
  paste something into a feedback/bug-report form yourself)
- Your personal dictionary, snippets, notes, or dictation history
- Your API keys
- Your name, email, or any account information (we don't have accounts)
- Location, contacts, browsing history, or anything from other apps

## 7. Children's privacy

Arc Flow is not directed at children, does not knowingly collect
information from children, and has no account system that could collect
such information in the first place.

## 8. Changes to this policy

We may update this policy as Arc Flow's features change. Meaningful changes
will be reflected here, in this repository, with an updated effective date
at the top of this document.

## 9. Not open-source

Arc Flow is free to use, but it is not open-source software — the source
code is not published or licensed for reuse. See [LICENSE](LICENSE) in this
repository for the full terms.

## 10. Contact

Questions about this policy, or about your data, can be sent to
helloarcflow@gmail.com.
