# Cozy Kingdoms Downloads

## Current playtest: v0.18.3 — protocol 10

**[Download Windows client](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261101-protocol10/CozyKingdoms-v0.18.3-protocol10-Windows-Client.zip)**

**[Download Windows dedicated server](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261101-protocol10/CozyKingdoms-v0.18.3-protocol10-Windows-Server.zip)**

**[Download Android APK](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261101-protocol10/CozyKingdoms-v0.18.3-protocol10-Android-debug.apk)**

[Release notes and all assets](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/playtest-20261101-protocol10) · [SHA256 checksums](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261101-protocol10/SHA256SUMS.txt) · [Validation report](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/playtest-20261101-protocol10/VALIDATION.json)

Use the client and server from this same release. Older protocol 8/9 packages cannot connect to this protocol 10 server.

### What is new

- Player-built dirt and stone roads, builder assistance, connected biome artwork and movement bonuses.
- Updated inventory/map/building artwork, loading screens, castle waypoints, compass/clock layout and build menus.
- New worlds are 110×79, about half the former area, with 25% forage and double stone targets. Existing saved worlds keep their recorded size/profile.
- Loose equipment expires after 30 seconds; held and stored equipment is preserved.
- Consistent menu backgrounds/music, a shuffled gameplay playlist with new song starts every five active gameplay minutes, and separate **Music** and **Effects** volume sliders.
- Online bow, arrow-hit, melee, bomb, door, menu, fishing, low-health and respawn sounds; corrected facing and northward aiming.

### Windows: play or host

Extract the complete client ZIP and run `CozyKingdoms.exe`. Keep its PCK beside it. Offline play is available without a server.

For online play select **Multiplayer**, then **Little Wars** when its configured host is available. Enter your name/faction and connect. On the server PC choose **This PC (host)**; for another host/LAN address use **Other address**.

To host, extract the complete server ZIP and run **server.bat**. Keep the EXEs, console companion and PCK together. Leave its console open. The host still needs inbound **UDP 17174** firewall/router routing for internet access. No relay/join-code service or automatic router/firewall changes are included.

Stop the old server normally and back up its `.ckworld` and `.bak` before upgrading. This update does **not** delete or reset saves. The launcher retains `friends_family_playtest.ckworld` under `%APPDATA%/Godot/app_userdata/Cozy Kingdoms/multiplayer/worlds/`. Keep custom save/port settings if you use them. Never run two servers against the same save. Autosaves occur every 30 seconds; abrupt closure may lose progress since the last save. Windows x86-64 binaries are unsigned.

### Android: update without clearing saves

Install the new APK **over the existing main-game app**. **Do not uninstall or clear app data.**

The package remains `com.jmthacker1990.cozykingdoms`; versionCode increases to **183** and versionName is **0.18.3-protocol10**. The **same existing signing key/certificate** is preserved and both APK signatures were verified. This preserves the Android in-place update path. Separately named old multiplayer-test apps use different package IDs.

The APK is ARM64. Package/version, signature, ZIP integrity and 16KiB alignment passed; all **239 shared game scripts** match the tested Windows client/server. No physical Android device was connected, so a real installation, touch controls, phone audio/performance and Android-to-server connection have **not** been tested here.

### What was tested

The actual exported Windows client/server passed loopback ENet connection, initial world sync, movement/UI and server checkpoint saving. **18 online audio checks** passed, including captured non-silent mixed audio for the expected cues. The exported main menu and bounded offline gameplay also passed. Uploads are checked against GitHub's SHA256 asset digests.

This is a **prerelease playtest**. The short online sample ran about **58.6 FPS in an isolated 40×32 world with at most six soldiers**. It does not certify full-world/long-war performance or internet reachability. Physical Android and WAN testing remain unverified. Keep backups and use trusted playtesters.

### Previous releases

[Protocol 9 playtest](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/playtest-20261031-protocol9) and [v0.18.1 / protocol 8](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/v0.18.1) remain available for rollback. Keep matching versions together.
