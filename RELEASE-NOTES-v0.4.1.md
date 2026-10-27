# CRACK Spacewar v0.4.1

This release updates compatibility guidance for CRACK Steam build **26250299**.
The drag-and-drop files and `winmm.dll` are unchanged from v0.4.0. Install beside
`CRACK.exe` and launch through Steam normally, with no launcher or arguments.

The maintainer reports successful testing with the updated game. The exact
multiplayer scenarios and player count were not recorded. All players in a
session must use the same game build and package revision. Build 26226661 has
historical structural evidence and a prior user-reported successful session.
Other and future builds are unverified; no compatibility guarantee is made.

The old v0.3 launcher can reject updated assemblies with “The original game
component changed.” Clear its custom Steam Launch Options entry and remove
`-onlinefix` before using this native package.

The release includes the drag-and-drop package, complete source archive,
license notices, and SHA-256 sums. No game binaries are included.
