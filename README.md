# Intera Browser - Releases

This repo publishes only the update manifest (`version.json`) and packaged installers as GitHub Releases for Intera Browser. It does not contain source code.

The installed app checks `version.json` on the `main` branch to detect new versions and downloads the matching release asset when the user updates.

## Release asset naming (required)

Every release must attach exactly these two asset names, so the stable
`.../releases/latest/download/<name>` links always resolve to the newest
build without editing `version.json`'s URLs each time:

- `InteraBrowser.exe` - the self-contained app binary (installer downloads this directly at install time)
- `Intera-Installer.exe` - the online-bootstrapper installer (Inno Setup), fetches `version.json` + `appUrl` at install time and always installs whatever is currently latest

Only `version` and `notes` in `version.json` need to change per release;
`installerUrl` and `appUrl` stay pointed at `releases/latest/download/...`.
