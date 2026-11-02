# Cozy Kingdoms downloads

**Windows/Android clients 0.19.1 · server 0.19.0 · multiplayer protocol 10**

Little Wars now connects to **74.128.141.148, UDP 17174**. This client address fix works with the existing server.

Download the compatible client and server below. Source code is maintained separately in the private source repository.

| Download | What to run |
|---|---|
| [Windows client](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.19.1/CozyKingdoms-v0.19.1-Windows-Client.zip) | Extract the whole ZIP, then run `CozyKingdoms.exe`. |
| [Windows dedicated server (unchanged 0.19.0)](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.19.0/CozyKingdoms-v0.19.0-Windows-Server.zip) | Extract the whole ZIP, then run `server.bat`. |
| [Android APK (ARM64)](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.19.1/CozyKingdoms-v0.19.1-Android-debug.apk) | Install over the existing app to keep its data. |

[0.19.1 release and notes](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/tag/v0.19.1) · [Checksums](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.19.1/SHA256SUMS.txt) · [Validation record](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases/download/v0.19.1/VALIDATION.json) · [Previous releases](https://github.com/jmthacker1990-ops/Cozy-Kingdom-Download/releases)

## What changed

**0.19.1:** updated the built-in Little Wars address and increased Android versionCode to 191 while retaining the original signing identity. The game content below is included from 0.19.0; the dedicated server is unchanged.

- New faction castles with four courtyard arrow turrets, two respawning gate guards, solid walls and throne-room routes.
- Walkable castle wall tops: use either courtyard side door to go up, then press **E at the matching stairs** to descend.
- Corrected army navigation, gate depth, tower-face restrictions and throne-entrance ledges.
- Courtyard/exterior building placement, grid-aligned gates in new worlds, and corrected Barracks (4×4) and Archery Range (6×4) footprints. Unused castle log storage is removed.
- Respawn countdowns and movement-state fixes.
- New worlds use **78×56 cells**, **12.5% baseline forage**, and **4× baseline stone**; revised swamp shoreline frogs, doubled swamp fireflies/water plants, and no new snow insects.
- Includes the existing dirt/stone roads, map and inventory menus, music, effects and volume controls.

## Windows setup

Extract the **complete** ZIP to a writable folder. Keep the EXE, console companion and PCK together; the Godot editor is not required. Do not run from inside the ZIP. Windows x86-64 is required and the executables are unsigned.

Use **0.19.1 clients with the existing 0.19.0 protocol-10 server**. Updating the server is not required for this address fix.

## Running server.bat and joining

1. Stop the old server normally and back up its save before replacing the complete server package.
2. Extract the Server ZIP and run `server.bat`. Keep the console open for the war to advance. It listens on **UDP 17174** and autosaves every **30 seconds**.
3. On the hosting PC, open the client and choose **Multiplayer → This PC (host)**.
4. Other players can use **Little Wars** for the configured shared host, or **Other address** for another host's IP/hostname, then enter their name and faction and connect.

For players outside the host's home network, the host must allow inbound UDP 17174 through the firewall and forward UDP 17174 on the router to the host PC. Guests do not need to forward ports. There is no join-code relay or automatic router setup.

Closing the server abruptly can lose progress since the last completed autosave. Never run two server processes against the same save.

## Existing saves and updates

The update does not reset player or server data. The server save remains at:

```text
%APPDATA%\Godot\app_userdata\Cozy Kingdoms\multiplayer\worlds\friends_family_playtest.ckworld
```

Back up that file and its `.bak` before updating. Keep the same server address/host selection when reconnecting to reuse the saved player identity.

Existing worlds retain their saved generation settings and castle root positions. The new population defaults and gate alignment apply to newly generated worlds. Do not delete a save to resolve a startup error.

The Android package remains `com.jmthacker1990.cozykingdoms`, with the **same signing certificate**, versionCode **191**, and versionName `0.19.1-protocol10`. Install the APK over the previous app. **Do not uninstall or clear app data.** This APK uses the existing test signing identity.

## Validation and limits

Both final client exports passed their original guarded build checks. A fresh bounded Windows loopback test against the unchanged 0.19.0 server passed joining, world synchronization, movement, isolated checkpoint saving and existing HUD/menu/aiming checks.

The new address is verified in both packages. The Windows pack differs from 0.19.0 only in its project-version data and connection-address resource. All 247 shared compiled game scripts match the previous client and unchanged server.

The APK passed signature, original-certificate equality, package metadata, Internet-permission, ZIP-integrity and 16 KiB alignment checks. Install over the existing app; do not uninstall or clear data.

The owner confirmed cellular connectivity to the new address using the previous client before this rebuild. The rebuilt APK has not been installed or played on a physical phone in this release session. Short bounded tests do not establish sustained performance in long wars or large battles. See `VALIDATION.json` for the exact scope.

Report problems with the version, platform, offline/online mode, hosting arrangement and what happened immediately before the issue. Keep player identities, real saves and signing files private.
