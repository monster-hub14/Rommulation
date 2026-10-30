# Rommulation

**Author: Monster Review**

<img src="https://github.com/monster-hub14/Rommulation/releases/download/v1.1.1/rommulation-icon.png?v=1.1.1" alt="Rommulation CRT TV and controller" width="192">

A native Nintendo Switch client for your RomM library, with integrated retro gameplay and automatic downloads of compatible missing engines. RetroArch is not required.

<a href="https://www.buymeacoffee.com/monsterreview"><img src="https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png" alt="Buy Me a Coffee" width="200"></a>

## Download

[Download Rommulation 1.5.0](https://github.com/monster-hub14/Rommulation/releases/download/v1.5.0/Rommulation-1.5.0.zip) | [Releases](https://github.com/monster-hub14/Rommulation/releases)

Extract the complete ZIP to your SD root and merge/replace its files. Keep the existing app folder to preserve saved login, downloads and saves. Internal paths remain compatible with earlier Rom NX versions.

Connect to your own RomM server using device pairing or username/password fallback. Saved sign-in reconnects automatically. Browse consoles, press X to download, then A to play. Right stick click opens the gameplay menu.

## Optional automatic app updates (1.5.0)

Automatic updates are **ON by default**. Install the complete 1.5.0 ZIP once to add the updater. From the sign-in or library screen, press **ZL** to open **App updates**, then **X** until **Automatic updates: OFF** appears. Press **B** to return. Your choice is saved after restarting; switching it off cancels an active update transfer and prevents automatic checks/installations.

You can still press **A** in App updates to check manually, then **A** again to install a verified download. Manual checking leaves automatic updates off. With automatic updates enabled, a verified update waits for the console menu and a five-second countdown; **B** postpones it. Gameplay is never interrupted. **Y** restores the previous verified app and disables automatic updates. Login, downloads and saves are retained.

The updater uses stable GitHub releases, HTTPS, SHA-256 checks and two app slots for recovery. Gameplay engines refresh from the app version's verified catalog when needed; installed engines remain usable offline. The bootstrap/hbmenu icon needs the complete ZIP for future changes. See [UPDATES.md](UPDATES.md) for installation, recovery and manual-update details. Rommulation-specific physical update/relaunch testing is still pending.

The header now reads **Rommulation — By Monster Review**, with the author credit in smaller text.

## Genesis / Mega Drive startup fix in 1.4.3

[Download Rommulation 1.4.3](https://github.com/monster-hub14/Rommulation/releases/download/v1.4.3/Rommulation-1.4.3.zip).

Fixes a null-pointer crash when Genesis Plus GX clears its disc interface for a cartridge game. Also preserves complete battery saves, accepts valid trimmed SRAM files, and logs core initialization/load/first-frame progress. The actual Sega core reproduces the old crash with an original generated test cartridge; the fixed host runs 120 frames with video/audio, two input ports, state restore and battery-save reload checks. **Verified on Switch, October 29, 2026:** the user confirmed Genesis/Mega Drive games now launch and play, with two-player mode working as well. The fix is retained in 1.5.0. This build retains the NES Joy-Con fixes and the verified N64 controller layout.

## Joy-Con assignment fix in 1.4.2

[Included in the current 1.4.3 release](https://github.com/monster-hub14/Rommulation/releases/download/v1.4.3/Rommulation-1.4.3.zip).

Fixes a saved mixed-controller setup leaving NES player one empty on a regular Switch. With only attached Joy-Con, they become P1; detached controllers are assigned to the available player slots even if a lower Switch controller slot is empty. Delayed controller detection and attaching/detaching Joy-Con are handled without merging players. The verified N64 external-P1 / attached-P2 layout is retained when both devices are present. Driver tests pass; this new fix still needs a physical regular-Switch NES retest. This controller fix is included in 1.4.3.

## Local multiplayer

For an external controller plus Joy-Con attached to the Switch, choose **Two players / external P1 + attached Joy-Con P2** in Plus > Controllers. The external controller is P1 and both attached Joy-Con together are P2. Then choose two-player mode inside the game.


**Verified on Switch:** the user confirmed N64 multiplayer now works properly in 1.4.1, including the external-controller P1 / attached-Joy-Con P2 fix (October 29, 2026).

Press **Plus** in the library, choose **Two players / one sideways Joy-Con each**, detach the Joy-Con and press **SL + SR** on each in the pairing screen. Select two-player mode inside the game. Two full controllers are also supported. During games, use right-stick click on a full controller or **SL + SR + Plus/Minus** on a single Joy-Con to open the pause menu, then choose **Controllers / player setup**.

For four-player PlayStation games such as Crash Bash, choose **Four players / full controllers** or **Four players / one sideways Joy-Con each** before launching. Pair four controllers in player order, then choose four players inside the game. PlayStation Multitap is enabled automatically on Port 1; the pause menu can switch it to Port 2 for games that require it. Four individual Joy-Con means four physical Joy-Con.

Two-player play was confirmed working by the user. Four-player PlayStation input and the actual core Multitap protocol pass host tests; four-player gameplay still needs Switch testing. NES, SNES and Genesis-family engines retain two controller ports. **Game Boy/GBA link-cable multiplayer is not implemented.** See MULTIPLAYER.md in the release package.

## Verified working setup

Genesis/Mega Drive gameplay and two-player mode were user-tested and confirmed working in 1.4.3 on October 29, 2026. This confirms the reported gameplay and controller results; Sega CD, every game, and every peripheral are not covered by that report.

N64 multiplayer and the attached-Joy-Con player-two fix were user-tested and confirmed working in Rommulation 1.4.1 on October 29, 2026. This confirmation covers the reported controller arrangement; it does not claim every N64 game, peripheral or four-controller combination was tested.

Single-player gameplay and the 1.2.0 two-player build were user-tested and verified working on **Atmosphere 23.0.1 AMS 1.12.1 E**.

## Engines

Includes SNES, PlayStation, Nintendo 64, NES/Famicom, Genesis/Mega Drive, Game Boy/Color and GBA components. Missing compatible engines are downloaded over HTTPS, verified and kept on SD. Some systems need user-provided BIOS files. The catalog supports future compatible engines; it does not make every RomM platform playable. Nintendo 64 is included in 1.4.1; Dreamcast integration remains pending.

SNES/PlayStation gameplay, N64 multiplayer, and Genesis/Mega Drive gameplay with two-player mode were confirmed on Switch. Native builds, executable/package checks and public download hashes pass. Additional systems and the automatic installer still require Switch hardware testing.

## Source and licenses

[Rommulation-Source.zip](https://github.com/monster-hub14/Rommulation/releases/download/v1.5.0/Rommulation-Source.zip) contains corresponding source, build scripts and notices. Original app code is MIT licensed; emulator components retain their own licenses, including applicable noncommercial terms. No commercial games, proprietary BIOS, or account credentials are distributed. This is an independent community client.

