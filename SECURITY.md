# Security Policy

## Please do not open a public issue for sensitive reports

If you've found any of the following, **do not** report it through a public
GitHub issue — email me instead so it can be handled privately before any
details are public:

- A security vulnerability in the Arc Flow application (e.g. a way to
  execute code, escalate privileges, or bypass a security control)
- Exposure of secrets, credentials, or API keys — yours or Arc Flow's
- A way to bypass licensing or access paid/restricted functionality without
  authorization
- Exposure of private user data (yours or someone else's)
- Account-specific problems that involve personal or billing information

Public bug reports and feature requests (the normal kind — a crash, a UI
bug, a missing feature) should still go through
[GitHub Issues](../../issues) as usual; this policy is specifically for
reports that shouldn't be visible to the public before they're resolved.

## How to report

Email **helloarcflow@gmail.com** with:

- A clear description of the issue and its potential impact
- Steps to reproduce it, or a proof of concept if you have one
- The Arc Flow version and OS you tested on
- Whether you'd like credit for the report, and how you'd like to be named

Please allow a reasonable amount of time to investigate and ship a fix
before disclosing the issue publicly. I aim to acknowledge reports within
a few business days.

## Supported versions

Arc Flow auto-updates by default, so only the **latest released version**
is generally supported and patched. If you're reporting an issue, please
confirm it still reproduces on the latest release from the
[Releases](../../releases) page first.

## Scope

This repository contains no application source code, so most reports will
concern the compiled application itself, its update mechanism, or its
optional cloud-connected features (see the app's in-app Privacy Policy for
what data is involved in each mode). Reports about third-party AI providers
you've connected your own account to (OpenAI, Anthropic, Google, Groq,
DeepSeek, etc.) should be directed to that provider, not here — Arc Flow
doesn't operate or control their infrastructure.
