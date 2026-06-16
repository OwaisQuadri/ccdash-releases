# ccdash-releases

Auto-update feed + signed builds for [CCDash](https://github.com/OwaisQuadri/operator-hq)
(a macOS menu-bar app that schedules local Claude Code runs).

- **`appcast.xml`** — the [Sparkle](https://sparkle-project.org) feed the app polls.
  Served at `https://raw.githubusercontent.com/OwaisQuadri/ccdash-releases/main/appcast.xml`.
- **Releases** — each `vX.Y` release attaches the notarized `CCDash-X.Y.dmg`.

Builds are produced from the `operator-hq` repo via
`CCDash/scripts/build-dmg.sh` (Developer-ID signed + notarized) and published here by
`CCDash/scripts/publish-appcast.sh` (EdDSA-signs the DMG, cuts the GitHub release, prepends
the appcast item). Updates are verified by Developer-ID **and** an EdDSA signature.

## Install

Download the latest `CCDash-*.dmg` from [Releases](../../releases), open it, drag CCDash to
Applications, launch. After the first install the app keeps itself up to date automatically.
