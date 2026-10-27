# CRACK Spacewar

A Windows x64, drag-and-drop Spacewar integration for CRACK Steam build
**26226661**. It provides a small `winmm.dll` forwarding proxy and app ID
configuration; the game and its original Steam API are not included or modified.
This is an experimental prerelease: the user reported that v0.4 worked in the
game, but player count and detailed multiplayer scenarios were not recorded.

## Installation

1. Close CRACK. Locate its Steam installation folder containing `CRACK.exe`.
2. Back up any existing files named `winmm.dll`, `CRACK-Spacewar.ini`, and
   `steam_appid.txt` before extracting the three files from the release ZIP
   beside `CRACK.exe`. Do not combine this DLL with another `winmm.dll` mod.
3. If you previously installed the v0.3 launcher, clear its custom Steam launch
   option once. New installations require no launch arguments or separate EXE.
4. Start Steam and launch CRACK with its normal Play button. Confirm Spacewar
   presence and use the Steam overlay to invite friends. All participants
   should use the same game build and this same release.

## Troubleshooting and removal

Check that the three files are beside `CRACK.exe`, Steam is running, no old
launcher argument remains, and the game and package versions match. The loader
may write `CRACK-Spacewar-Loader.log` when its multimedia forwarding first
initializes; it is diagnostic evidence, not proof of a multiplayer connection.
To uninstall, close the game, remove these three installed files and restore
your backups. The log may be removed separately.

## Source and validation

See [BUILD.md](BUILD.md) for build dependencies and native probe tests. The
release includes a tested binary; source builds depend on the local Windows
export set and toolchain and are not guaranteed to be byte-identical. The
project is licensed under [MIT](LICENSE); see [third-party notices](THIRD-PARTY-NOTICES.md).
