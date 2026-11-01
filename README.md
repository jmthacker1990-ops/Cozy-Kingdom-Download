# Cozy Kingdoms Downloads

Latest playtest: [v0.18.1](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/v0.18.1).

# Cozy Kingdoms v0.18.1 playtest

Windows client, Windows dedicated server and Android use multiplayer **protocol 8**.
Use matching v0.18.1 packages. Windows requires x86-64; Android requires ARM64.
This is a public prerelease; offline play remains available without a server.

## Install and play

Windows: extract the entire client ZIP and run `CozyKingdoms.exe`. Keep the PCK
beside the executable. Choose **Play Offline** for a local game, or **Multiplayer**
to connect to a dedicated server. Windows binaries are unsigned.

Android: install `CozyKingdoms-v0.18.1-debug.apk`, allowing installation from your
download app if prompted. Package identity remains `com.jmthacker1990.cozykingdoms`,
version code 181. The APK uses the same debug signing certificate as the previous
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

The launcher deliberately retains `v0.18.0.ckworld` under
`%APPDATA%/Godot/app_userdata/Cozy Kingdoms/multiplayer/worlds/`.
Stop the old server and back up its `.ckworld` and `.bak` before upgrading.
Keep the previous build for rollback. Packaging does not touch live saves.
Existing fixed-world saves use the compatibility path; fresh worlds use seeded
procedural terrain. Do not run two servers against the same save.
Closing the console may lose progress since the last autosave. Downtime does not
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

King defeat stops new army spawns and announces victory. The default server
intermission for procedural worlds is 60 seconds, then a new war starts without disconnecting clients.
Older fixed-world saves retain the completed war instead of automatically resetting.
World state is reset for the new war while player identity remains persistent.
Leaving a client does not stop the server.

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

## v0.18.1 known issues

Severe 130-NPC slowdown remains (about 7 FPS in the measured Windows case); 28/70 gate/ranged navigation checks fail on both baseline and current code; multiplayer snapshot delivery can intermittently time out despite a passing repeat. See release notes. Physical Android and WAN validation remain outstanding.

## Current development status — October 31, 2026

The downloads linked below remain v0.18.1 (protocol 8). New development sources use protocol 9 and have not been packaged into a new tested release. Use matching client and server packages; do not mix these versions.

The planned multiplayer setup is one owner-operated server named **Little Wars**. Updated clients will offer Little Wars, This PC (host), and Other address. Players will not need to configure their own routers. The host still needs a reachable internet connection, inbound UDP 17174 and router forwarding. There is no active join-code or relay service, and internet connectivity has not yet been verified. Existing downloads retain the connection instructions below until a matching new release is published.
