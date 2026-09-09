# Native Tile

Native Tile is a macOS menu bar app for arranging windows, switching between
apps and windows, and previewing windows from the Dock. This repository hosts
its signed downloads, release notes, and update feed.

## Download and install

Native Tile requires macOS 14 or later. Each download supports Apple silicon
and Intel Macs.

1. Open [Releases](https://github.com/alexander-cato/native-tile-updates/releases) and choose a version. Prereleases are labeled Beta or Nightly.
2. Download `Native-Tile-<version>-macOS-universal.zip` and unzip it.
3. Move **Native Tile.app** to **Applications**, then open it.
4. Follow the setup prompts. Accessibility permission lets Native Tile arrange windows. Screen Recording permission enables window previews and compositor animations.

If the Releases page is empty, the first public download has not been published
yet. Installations from before in-app update support need one manual installation
of a supported version.

## Updates and channels

Open **Settings → General → Updates** to check for updates or select a channel.
Automatic checks are optional. Native Tile asks before installing an update.

| Channel | Updates offered | Intended use |
| --- | --- | --- |
| Stable | Stable releases | Everyday work |
| Beta | Stable and beta releases | Trying changes before stable release |
| Nightly | Stable, beta, and nightly releases | Testing development builds |

Beta and nightly builds may include unfinished changes or regressions. Switching
back to Stable waits for a stable version newer than the installed version; it
does not download an older app. The version shown in About identifies the build
installed on your Mac, even when you have selected a different update channel.

Stable versions use `major.minor.patch`. Beta versions add `-beta.N`. Nightly
versions include a timestamp and source identifier. Each release page contains
its changelog, compatibility details, download, and checksum.

## Download verification

Native Tile is signed with a Developer ID certificate and notarized by Apple.
In-app updates also verify the archive's Sparkle signature before installation.
Each release includes a `.sha256` file for checking a manual download.

In Terminal, change to the folder containing both downloaded files and run:

```sh
shasum -a 256 -c Native-Tile-<version>-macOS-universal.zip.sha256
```

Replace `<version>` with the downloaded version. An `OK` result confirms that
the ZIP matches its published checksum. Keep macOS security checks enabled.

## Privacy

Update checks and downloads contact GitHub. GitHub receives normal connection
information, including your IP address. Native Tile does not upload window
contents, window titles, or diagnostic recordings during update checks, and
does not enable Sparkle system-profile reporting. Window management runs locally.

## Troubleshooting

- **No update offered:** check the selected channel and the installed version. Returning from a prerelease to Stable may require waiting for a newer stable build.
- **Download fails:** retry when your connection is available, or download the ZIP from the release page. Do not install an archive that fails its checksum or macOS security checks.
- **Window controls do not work after installation:** review Native Tile's Accessibility permission in System Settings → Privacy & Security, then quit and reopen the app.
- **Previews are unavailable:** review Screen Recording permission in the same settings area. macOS may ask you to reopen the app after a permission change.

[Report a problem](https://github.com/alexander-cato/native-tile-updates/issues)
with your macOS version, Native Tile version, update channel, and steps to
reproduce it. Do not include private window contents or credentials.

## Remove Native Tile

Quit Native Tile from its menu, then remove it from Applications. You can remove
its Accessibility and Screen Recording permissions in System Settings. Removing
the app does not delete its saved preferences.
