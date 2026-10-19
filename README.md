# Cozy Kingdoms downloads

Playable prerelease **v0.18.0**. This repository contains download instructions and releases only.

- [Android APK](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.18.0/CozyKingdoms-v0.18.0-debug.apk)
- [Windows client ZIP](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.18.0/CozyKingdoms-v0.18.0-Windows-Client.zip)
- [Windows dedicated server ZIP](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.18.0/CozyKingdoms-v0.18.0-Windows-Dedicated-Server.zip)

# Cozy Kingdoms v0.18.0 playtest

Windows client, Windows dedicated server and Android use multiplayer **protocol 8**.
Use matching v0.18.0 packages. Windows requires x86-64; Android requires ARM64.
This is a public prerelease; offline play remains available without a server.

## Install and play

Windows: extract the entire client ZIP and run `CozyKingdoms.exe`. Keep the PCK
beside the executable. Choose **Play Offline** for a local game, or **Multiplayer**
to connect to a dedicated server. Windows binaries are unsigned.

Android: install `CozyKingdoms-v0.18.0-debug.apk`, allowing installation from your
download app if prompted. Package identity remains `com.jmthacker1990.cozykingdoms`,
version code 180. The APK uses the same debug signing certificate as the previous
main-game APK, allowing an in-place update without clearing app data. Separately
labeled old multiplayer test apps are different packages. Use landscape touch
controls. Reconnect after app suspension. This build needs physical-device testing.

## Run a dedicated server

Extract the complete server ZIP and double-click `Start-Server.cmd`. No Godot
editor is required. Keep its EXE, console launcher and PCK together. The server
uses **UDP 17174**, autosaves every 30 seconds and advances the war without clients.
Allow inbound UDP 17174 in Windows Firewall. Run one server per save file and port.
Optional arguments follow the script, e.g. `Start-Server.cmd --port=17175` or
`Start-Server.cmd --save=C:/CozyWorlds/my-war.ckworld`.

The launcher uses a new `v0.18.0.ckworld` under
`%APPDATA%/Godot/app_userdata/Cozy Kingdoms/multiplayer/worlds/`.
**A fresh war is required when upgrading from v0.17.x** because the authored world
entity layout changed. No automatic old-world migration is supplied. Old saves
are left untouched; retain the previous build to resume them. Incompatible saves
are rejected instead of silently overwritten. Saves created with v0.18.0 support
restart and reconnect. Back up `.ckworld` and `.bak` files with the server stopped.
Closing the console can lose progress since the last autosave; downtime does not
advance the simulation. Direct EXE launches without `--save` use `default.ckworld`.

## Connect to multiplayer

Enter the server IP without a port suffix, select a faction, then connect on
the default port 17174. Windows clients can use `-- --port=17175` for a custom
port. On the server PC use `127.0.0.1`; on another PC or phone use the server's
LAN IPv4 address. Internet connections require a reachable public address and UDP
port forwarding. CGNAT, VPN routing and guest-network isolation may prevent access.
There is no lobby browser, relay or NAT traversal. Use trusted playtesters.

Returning players retain their faction and state using a private local token
stored per host and port. Reuse the same address; clearing app data loses that
token. There is no account recovery. Eight players may connect, with sixteen
retained identities per world. For a second client on one PC, use
`CozyKingdoms.exe -- --connect=127.0.0.1 --identity-file=user://multiplayer/second.cfg`.

King defeat stops new knight and archer spawns. After five seconds, a victory
popup offers **Back to Game** or **Back to Main Menu**. The completed war remains
playable; it does not automatically reset. Start a server with a different save
path for a fresh war. Leaving a client does not stop the server.

## Changes and limitations

Includes the animated main menu, matching menu buttons, settings improvements,
victory popup, compass clock, construction grid and wall corners, barricades,
equipment targeting, wolves and bunnies, frog idle animations, water ripples,
and regional plants at 1x scale. Construction artwork now matches the finished
wall/gate offsets. All packages share the same gameplay and protocol sources.

Some wall/corner placement combinations still need visual tuning. Cosmetic effects
may be local or rebuilt after a restart. Comic Sans Bold is used where installed;
other platforms use a font fallback. No encrypted transport, prediction/lag
compensation or interest management is supplied. WAN latency, long-running servers
and physical Android performance remain unverified. This is a playtest, not a
production-hardened hosting service.
