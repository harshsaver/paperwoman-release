# Paperwoman — Releases

Public download + auto-update feed for **Paperwoman**, a macOS menu-bar utility
that lays a soft paper-texture matte over your screen.

- **Download the latest version:** see [Releases](https://github.com/harshsaver/paperwoman-release/releases).
- **Update feed (Sparkle):** [`appcast.xml`](appcast.xml) — the app checks this
  automatically. Feed URL: `https://raw.githubusercontent.com/harshsaver/paperwoman-release/main/appcast.xml`

The source code lives in a separate repository.

## Install

1. Download `Paperwoman.dmg` from the latest release.
2. Open it and drag **Paperwoman** to your Applications folder.
3. Launch it. The app is Developer ID–signed and notarized by Apple, so it opens
   with no Gatekeeper warning. For auto-updates to install cleanly, keep it in
   `/Applications`.

Requires macOS 14 (Sonoma) or later · Apple Silicon or Intel.

## Publishing a release (maintainer)

1. In the source repo, bump `VERSION`, then `./build.sh --notarize` → `dist/Paperwoman.dmg`.
2. Get the signature: `.build/artifacts/sparkle/Sparkle/bin/sign_update dist/Paperwoman.dmg`.
3. Create a GitHub Release here tagged `vX.Y.Z` and attach `Paperwoman.dmg`.
4. Add an `<item>` to `appcast.xml` (version, notes, enclosure URL, `sparkle:edSignature`,
   `length`) and commit. Installed apps pick it up on their next check.
