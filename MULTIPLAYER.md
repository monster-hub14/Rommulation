# Local multiplayer setup

**Verified October 29, 2026:** N64 multiplayer now works properly in Rommulation 1.4.1, including an external controller as P1 and both attached Joy-Con as P2.

1. Install the complete Rommulation 1.4.2 ZIP so the launcher and all engines are updated. Existing login, games and saves remain in their original folders.
2. In the library, press Plus to open Controllers. Choose **Two players / one sideways Joy-Con each**. Detach the Joy-Con and hold each horizontally.
3. In the Switch pairing screen, press **SL + SR** on the first Joy-Con for player one, then on the second for player two. Finish the pairing screen. You can instead choose **Two players / full controllers** for two Pro Controllers or two Joy-Con pairs.
4. Download/open the game and select its own two-player mode. The app cannot turn a single-player game into a two-player game.

During gameplay, open the pause menu with right-stick click on a full controller, or **SL + SR + Plus/Minus together** on a single Joy-Con. Choose **Controllers / player setup** to change assignments. Either player can use the pause menu. A disconnected controller pauses gameplay and releases its game inputs; reconnect and resume explicitly.

## Four-player PlayStation

Before launching the game, press Plus in the library and choose **Four players / full controllers** or **Four players / one sideways Joy-Con each**. Pair all four controllers in player order. Four sideways Joy-Con require four physical Joy-Con; a pair provides two players. Launch a game that supports four players, such as Crash Bash, and select its multiplayer mode.

The engine automatically enables a virtual PlayStation Multitap on Port 1. If a game expects Port 2, use **Multitap** in the gameplay pause menu to switch ports. Changes apply on resume; some games require restarting afterward. Returning to a one/two-player setup disables Multitap. The pause menu shows P1 through P4 connection status. An active player disconnecting pauses gameplay and releases their buttons. This is local multiplayer on one Switch; online multiplayer is not included.

## Four-player Nintendo 64

Choose a four-player controller profile before launching a supported N64 game. The integrated engine connects four native controller ports, with no Multitap. Pair four physical controllers in player order, then choose multiplayer inside the game. Full controllers are recommended for the control stick, C-stick and D-pad. Four sideways Joy-Con are also selectable, with fewer directly accessible controls; see N64-BUILD.md. Inactive ports are detached when returning to a one/two-player profile. The user confirmed N64 multiplayer works properly in 1.4.1 on October 29, 2026, including external-controller P1 / attached-Joy-Con P2. This does not establish every four-controller combination or every game.

## Controls

Each Joy-Con's stick and face buttons rotate for horizontal use. The left Joy-Con's direction buttons become A/B/X/Y; its stick is movement. The right Joy-Con's face buttons rotate in the opposite direction and its stick is movement. SL/SR provide L/R. Plus or Minus provides Start; stick click provides Select. The outer L/ZL or R/ZR buttons provide L2/R2 for digital PlayStation controls. The pause chord is suppressed so it cannot leak Start or shoulder presses into gameplay. Full controllers keep their previous button mapping and have more comfortable access to every button.

Single Joy-Con stick click does not sign out of the library. To sign out, use Minus on a full controller; you can pair the two Joy-Con together using the one-player setup.

## Supported multiplayer scope

This implements two independent controller ports for ordinary local gamepad multiplayer on the included NES/Famicom, SNES, PlayStation and Genesis-family engines. It applies by engine, not by a hardcoded game list or RomM server. The game must itself support two-player play; some require selecting that mode from the title screen or pressing player two's Start.

Game Boy/Color and GBA engines currently emulate one handheld. Their link-cable/wireless games need multiple emulated machines and synchronization; assigning a second Joy-Con does not provide that. The setup screen explains the limitation and does not claim link play. Special peripherals, analog-only requirements, multitaps on non-PlayStation engines and universal per-game compatibility are not established. Dreamcast is not an included engine.

## Validation

The user confirmed the 1.2.0 two-player build works on Switch. Host tests now exercise four isolated input slots, independent button releases, both sideways layouts, pause suppression, disconnects, analog routing and two-player limits. Tests compile the actual vendored PCSX-ReARMed serial pad implementation and frontend adapters, checking four Multitap slots on Port 1, no ghost fifth controller, Port 2 mapping and two-player fallback. The real SNES core retains its two-port smoke test. These checks do not execute Crash Bash or replace physical four-controller Switch testing. Native executable/package checks cover the launcher and all seven engines. N64 tests execute the actual upstream input conversion for four players, analog control stick and C-stick. The user has confirmed N64 gameplay and the mixed-controller multiplayer fix on Switch. Wider performance and per-game coverage remain unverified.

For an external controller plus Joy-Con attached to the Switch, choose **Two players / external P1 + attached Joy-Con P2** in Plus > Controllers. The external controller is P1 and both attached Joy-Con together are P2. Then choose two-player mode inside the game.

## Regular Switch NES controls in 1.4.2

Saved controller preferences are now resolved against connected devices. An attached pair works as P1 when no external controller is connected, even after saving the mixed-controller layout. Detached Joy-Con use available Switch controller slots without requiring an unused lower slot to be filled. Use Plus > Controllers > Two players / one sideways Joy-Con each for detached two-player play, pair with SL + SR, then choose the game’s multiplayer mode. Hold the Joy-Con horizontally.

For attached Joy-Con as P2 with an external P1, keep the mixed profile; it is retained when both devices are connected. Disconnects keep the other player in place. Changing layouts pauses and clears held inputs before resuming. Switch Lite integrated controls remain supported. Changes are covered by simulated driver tests; a physical regular-Switch NES retest is pending. Gameplay logs report player-to-device assignments when they change.
