# About releases

Compiled Arc Flow builds (MSI installer, portable ZIP/EXE) are **not**
committed to this repository — they're published as downloadable assets on
the [Releases](../../../releases) page, alongside each version's release
notes and SHA256 checksums.

This `releases/` folder exists only to document that process; it does not
and should not contain any binaries itself.

## Where to actually get a build

- [Releases page](../../../releases) — the canonical source, every version
- The Arc Flow website (linked from this repository's "About" section) —
  mirrors the latest release for users who prefer a direct download page

## Verifying a download

Every release includes a `SHA256SUMS.txt` (or equivalent) alongside the
installer/ZIP. Before running an installer — especially one from a mirror
rather than this page directly — verify it matches:

```powershell
Get-FileHash .\ArcFlow-Setup-<version>.msi -Algorithm SHA256
```

Compare the output against the checksum published on the release. If they
don't match, don't run the file — re-download it and check again, or reach
out via [SECURITY.md](../SECURITY.md) if you suspect tampering.

## Release naming

Builds follow a `ArcFlow-Setup-<version>.msi` / `ArcFlow-<version>-portable.zip`
naming convention. The version number matches what's shown in the app under
**Settings → About**.
