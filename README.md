<p align="center">
 <img width="200px" src="https://github.com/slexoff/VODLens/blob/main/Logo.png" alt="logo"/>
</p>

<h1 align="center">
  VODLENS</br>
  <a href="https://github.com/slexoff/VODLens/releases">
    <img src="https://badge.fury.io/gh/slexoff%2FVODLens.svg" alt="Version">
  </a>
  <a href="https://github.com/slexoff/VODLens/actions">
    <img src="https://github.com/telegramdesktop/tdesktop/workflows/Windows./badge.svg" alt="Windows build">
  </a>
  <a href="https://github.com/slexoff/VODLens/actions">
    <img src="https://github.com/telegramdesktop/tdesktop/workflows/MacOS./badge.svg" alt="macOS build">
  </a>
</h1>

<p align="center">

</p>

VODLens is a desktop application for parsing and analyzing CS2 and Dota 2 matches.

The app includes:

- embedded browser for HLTV, Dotabuff, and stats pages;
- local Python parser server started from the desktop app;
- CS2 tools: Match, Live, Stats, Demo Logs, Round Logs;
- Dota 2 tools: Prematch, Live GSI, Postmatch, Heatmap;
- JSON viewer with Preview / Code modes;
- configurable save paths and local server port.

## Download

Latest version: [Releases](https://github.com/slexoff/VODLens/releases/latest)

Which file to download:

- Windows: `VODLens-Setup-<version>.exe`
- macOS: `VODLens-<version>-mac.dmg`

## Windows Installation

1. Download `VODLens-Setup-<version>.exe` from the latest release.
2. Run the installer.
3. Start VODLens from the desktop shortcut or Start Menu.
4. Open `Settings` and choose the output directory.
5. Start the local server from the top bar when parser features are needed.

## Windows Update

Windows supports in-app update checking and installation.

1. Open `About`.
2. Click `Check for updates`.
3. If an update is available, download it.
4. Click `Restart and install`.

If update installation fails because the server process is still running, close VODLens completely and install the latest version manually from the release page.

## macOS Installation

1. Download `VODLens-<version>-mac.dmg` from the latest release.
2. Open the DMG file.
3. Drag `VODLens.app` into `Applications`.
4. Open terminal and set comman `xattr -dr com.apple.quarantine /Applications/VODLens.app`
5. Start VODLens.

If macOS blocks the app because it is not notarized yet:

1. Open `System Settings`.
2. Go to `Privacy & Security`.
3. Allow VODLens manually.

## macOS Update

macOS updates are manual for now.

1. Quit VODLens completely.
2. Download the latest `VODLens-<version>-mac.dmg`.
3. Open the DMG file.
4. Replace the old `VODLens.app` in `Applications`.
5. Start the new version.

The app may detect that a new version is available, but automatic install/restart is not used on macOS yet.

## First Run

Recommended setup:

1. Open `Settings`.
2. Choose the main output directory.
3. Review separate save paths for CS2, Dota 2, demo logs, and heatmaps.
4. If port `5050` is busy, change it in `Settings -> Server`.
5. Start the server from the top bar.

The current server status and active port are shown in the top bar.

## CS2 Features

- `Match`: parse HLTV match pages, live matches, and completed matches.
- `Stats`: parse HLTV stats using the embedded browser extension button.
- `Demo Logs`: upload local `.log` files and analyze grenades / pauses.
- `Round Logs`: inspect round-by-round kills, filters, and JSON export.

If HLTV shows a Cloudflare challenge, open the page in the embedded browser and complete the check there.

## Dota 2 Features

- `Prematch`: parse pre-match data.
- `Live`: live data through Dota 2 Game State Integration.
- `Heatmap`: record, save, load, replay, and share heatmap sessions.
- `Postmatch`: parse completed matches.

Dota 2 Live uses GSI as the primary data source. Steam Web API is used as an additional source for team names, leagues, and other metadata.

## Heatmap And LAN Page

When the local server is running, heatmap can be opened in a browser for stream capture or LAN viewing.

Available Heatmap buttons:

- `Open localhost`: open heatmap on the current machine.
- `Open LAN`: open the LAN URL when the server has network information.

The LAN page uses the server port configured in Settings.

## Saved Files

VODLens saves results into the selected output directory and separates data by category:

| CS2 | Dota2 | live sessions | postmatch results | demo logs | heatmap |
| --- | --- | --- | --- | --- | --- |

Paths can be changed in `Settings`.

## Troubleshooting

### Server does not start

- Check if the current port is already in use.
- Change the port in `Settings -> Server`.
- Restart VODLens.

### HLTV or stats page does not parse

- Open the page in the embedded browser.
- Complete the Cloudflare challenge if it appears.
- For stats pages, use the extension button in the embedded browser.

### macOS blocks the app

The app is not notarized yet. Use `Right click -> Open` or allow it in `System Settings -> Privacy & Security`.

### Windows update does not install

Close VODLens completely, make sure the `VODLens_Server` process is not running, then install the latest version manually from the release page.
