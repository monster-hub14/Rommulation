# Rommulation

**Author: Monster Review**

<img src="https://github.com/monster-hub14/Rommulation/releases/download/v1.1.1/rommulation-icon.png?v=1.1.1" alt="Rommulation CRT TV and controller" width="192">

A native Nintendo Switch client for your RomM library, with integrated retro gameplay and automatic downloads of compatible missing engines. RetroArch is not required.

<a href="https://www.buymeacoffee.com/monsterreview"><img src="https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png" alt="Buy Me a Coffee" width="200"></a>

## Download

[Download Rommulation 1.3.0](https://github.com/monster-hub14/Rommulation/releases/download/v1.3.0/Rommulation-1.3.0.zip) Â· [Releases](https://github.com/monster-hub14/Rommulation/releases)

Extract the complete ZIP to your SD root and merge/replace its files. Keep the existing app folder to preserve saved login, downloads and saves. Internal paths remain compatible with earlier Rom NX versions.

Connect to your own RomM server using device pairing or username/password fallback. Saved sign-in reconnects automatically. Browse consoles, press X to download, then A to play. Right stick click opens the gameplay menu.

## Local multiplayer

Press **Plus** in the library, choose **Two players / one sideways Joy-Con each**, detach the Joy-Con and press **SL + SR** on each in the pairing screen. Select two-player mode inside the game. Two full controllers are also supported. During games, use right-stick click on a full controller or **SL + SR + Plus/Minus** on a single Joy-Con to open the pause menu, then choose **Controllers / player setup**.

For four-player PlayStation games such as Crash Bash, choose **Four players / full controllers** or **Four players / one sideways Joy-Con each** before launching. Pair four controllers in player order, then choose four players inside the game. PlayStation Multitap is enabled automatically on Port 1; the pause menu can switch it to Port 2 for games that require it. Four individual Joy-Con means four physical Joy-Con.

Two-player play was confirmed working by the user. Four-player PlayStation input and the actual core Multitap protocol pass host tests; four-player gameplay still needs Switch testing. NES, SNES and Genesis-family engines retain two controller ports. **Game Boy/GBA link-cable multiplayer is not implemented.** See MULTIPLAYER.md in the release package.

## Verified working setup

Single-player gameplay and the 1.2.0 two-player build were user-tested and verified working on **Atmosphere 23.0.1 AMS 1.12.1 E**.

## Engines

Includes SNES, PlayStation, NES/Famicom, Genesis/Mega Drive, Game Boy/Color and GBA components. Missing compatible engines are downloaded over HTTPS, verified and kept on SD. Some systems need user-provided BIOS files. The catalog supports future compatible engines; it does not make every RomM platform playable. N64 and Dreamcast integration remains pending.

Previous SNES/PlayStation gameplay was confirmed on Switch. Native builds, executable/package checks and public download hashes pass. Additional systems and the automatic installer still require Switch hardware testing.

## Source and licenses

[Rommulation-Source.zip](https://github.com/monster-hub14/Rommulation/releases/download/v1.3.0/Rommulation-Source.zip) contains corresponding source, build scripts and notices. Original app code is MIT licensed; emulator components retain their own licenses, including applicable noncommercial terms. No commercial games, proprietary BIOS, or account credentials are distributed. This is an independent community client.
