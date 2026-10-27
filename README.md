# CRACK Spacewar

A Windows x64, drag-and-drop Spacewar integration for CRACK. Release v0.4.1
keeps the native `winmm.dll` payload from v0.4.0 unchanged and updates its
compatibility notes for the newer game build. The game and its original Steam
API are not included or modified.

## Compatibility and testing

The installed CRACK Steam build is **26250299**. The maintainer reports that
the updated game was tested successfully with this fix. The exact multiplayer
scenarios and player count were not recorded. Players joining one session must
use the same game build and fix package.

Build 26226661 has historical structural evidence and a prior user-reported
successful session. Future game builds remain unverified. Similar filenames
or an unchanged game architecture do not establish multiplayer compatibility.
See [compatibility/CRACK-Spacewar-v0.4.1.json](compatibility/CRACK-Spacewar-v0.4.1.json)
for the recorded evidence and its limits.

## Installation

1. Close CRACK and back up any existing `winmm.dll`, `CRACK-Spacewar.ini`, and
   `steam_appid.txt` from its game folder.
2. Extract those three files from the drag-and-drop ZIP beside `CRACK.exe`.
3. If you used the old v0.3 launcher, clear its custom Steam Launch Options
   entry and remove `-onlinefix`. New installs need no launcher or arguments.
4. Start Steam and launch CRACK normally. Use the Steam overlay to invite
   friends. All players must use the same game build and package revision.

Do not combine this proxy with another `winmm.dll` mod. For removal, close the
game, remove only these three package files, and restore your backups.

## Troubleshooting

The loader may create `CRACK-Spacewar-Loader.log` when system multimedia
forwarding initializes. That log does not prove Steam initialization or a
successful multiplayer session. The old launcher's “original game component
changed” error comes from its fixed assembly hash check; use the native DLL
package and clear the old launch option.

## Source and licenses

See [BUILD.md](BUILD.md) for build instructions and isolated native checks.
The project is MIT licensed. Rust attribution and license texts are in
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) and `third-party/rust/`.
