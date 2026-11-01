# Cozy Kingdoms Downloads

## Android update — protocol 9

**[Download Android APK (v0.18.2, protocol 9)](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261031-protocol9/CozyKingdoms-Android-v0.18.2-protocol9-debug.apk)**  
[Android validation report](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261031-protocol9/ANDROID_VALIDATION.json) · [Android SHA256 checksum](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261031-protocol9/ANDROID_SHA256SUMS.txt)

For ARM64 devices running Android 7.0 or later. This APK matches the new protocol 9 server.
Install it **over the existing main-game app**. **Do not uninstall or clear app data.**
The package ID and signing certificate are unchanged; version code increases from 181 to 182.
Both old and new signatures were cryptographically verified, preserving the Android in-place
update path. No device installation or save migration was performed here.

Package/signature/alignment checks passed, and all 225 game scripts match the tested
protocol 9 Windows client. **Physical-device launch, touch controls and Android-to-server
connection/performance remain unverified.** A themed-launcher-icon template warning remains.
This is a prerelease. Keep save backups and report device-specific problems.

## New Windows playtest — protocol 9

**[Download Windows client](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261031-protocol9/CozyKingdoms-Windows-Client-protocol9-20261031.zip)**  
**[Download Windows dedicated server](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261031-protocol9/CozyKingdoms-Windows-Server-protocol9-20261031.zip)**  
[SHA256 checksums](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261031-protocol9/SHA256SUMS.txt) · [Release notes and assets](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/playtest-20261031-protocol9)

These are the newer development packages labeled **playtest-20261031-protocol9**.
Their internal game version still reads 0.18.1; **protocol 9** identifies this update.
Use the client and server from this same release. Old protocol 8 packages cannot connect.

### Play

Extract the complete client ZIP and run `CozyKingdoms.exe`; keep its PCK beside it.
For multiplayer, choose **Little Wars**, enter your name/faction and connect.
Players do not configure routers or run the server. Offline play is also available.

### Host Little Wars

Extract the server ZIP and double-click `server.bat`. Keep its EXE, console companion
and PCK together. Leave the server running. On that same PC, open the client and
choose **This PC (host)**; on another LAN device, **Other address** can use the host's LAN IPv4.

Remote players still need the host to allow and forward **UDP 17174** to the server PC.
No router/firewall changes are performed automatically. The Little Wars endpoint is
configured in this client, but internet reachability has not been verified. No join-code
or relay service is active.

Back up existing saves and retain older packages before upgrading. This launcher uses
the separate `friends_family_playtest.ckworld` under
`%APPDATA%/Godot/app_userdata/Cozy Kingdoms/multiplayer/worlds/`.
Never run two servers against one save. It autosaves every 30 seconds; abrupt closure
may lose progress since the last completed save. Windows x86-64 binaries are unsigned.

### What passed and what remains open

Guarded checks passed for the exported-template menu, bounded offline gameplay and
matching client/server ENet connection, initial transfer, movement, continued snapshots
and server saving. A short online sample ran around **60 FPS in a 40×32 test world**.
ZIPs were read-back checked and GitHub asset digests matched local SHA256 hashes.

This is a **prerelease playtest**. Full-size-world performance and the earlier roughly
4 FPS online report are not yet certified as resolved. WAN reachability, long wars,
multiple remote clients, restart/save parity and physical Android require further validation.
Read the included `KNOWN_ISSUES.txt` and `README.txt`.

## Older Windows and Android downloads — protocol 8

The [v0.18.1 release](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/v0.18.1)
remains available for rollback and its existing Android APK.
**That Android APK uses protocol 8 and cannot join the new protocol 9 server.**
Keep matching old client/server packages together when using an old world/build.
The older release notes retain their known performance and navigation limitations.
