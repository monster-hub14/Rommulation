# 1.4.3 - Sega cartridge startup crash

- Fix a null-pointer dereference when Genesis Plus GX clears the disc interface after loading a Genesis/Mega Drive cartridge.
- Handle empty basic and extended disc callbacks while preserving valid disc registrations for PlayStation and Sega CD.
- Preserve a fixed-size Genesis SRAM buffer when saving, including erased/all-0xff saves; accept valid bounded trimmed SRAM files on reload.
- Log core initialization, ROM load, save load and first-frame progress.
- Reproduce the original crash using the actual vendored Sega core and an original generated cartridge; the fixed host passes 120 video frames, audio, two input ports, CPU RAM writes, state restore and save reload checks.
- Retain the NES Joy-Con assignment recovery and the verified N64 setup/rendering path.

Verified October 29, 2026: the user confirmed Genesis/Mega Drive ROMs now work on Switch, including two-player mode. 1.4.3 is the current stable release. The generated cartridge is not a commercial game; Sega CD and every individual Sega title are not validated by this test.

# 1.4.2 - Joy-Con assignment recovery

- Fix NES P1 receiving no input with attached Joy-Con after saving an external-P1 / attached-P2 profile.
- Resolve saved preferences against actually connected HID sources, including detached Joy-Con with empty lower controller slots.
- Retry assignment when HID arrives after startup; handle attached/detached transitions with held-input suppression.
- Keep surviving players in place on disconnect and avoid duplicate/merged inputs.
- Preserve the user-verified N64 mixed-controller layout and the working GLES renderer.
- Log player/device assignment changes for troubleshooting.

The old attached-only failure is reproduced by the driver regression. New attached, detached, late-HID, transition and Lite-style cases pass, alongside the N64 mixed and four-controller regressions. Physical regular-Switch NES testing is pending.

# 1.4.1 - N64 second-controller assignment

- Keep two N64 ports enabled in the default profile, as in the PlayStation engine; four-player profiles enable four ports.
- Add an explicit external-controller P1 / attached-Joy-Con P2 profile without a pairing applet that excludes attached controls.
- Keep attached Joy-Con on P2 in mixed full-controller layouts; preserve independent inputs and neutral disconnects.
- Preserve the user-confirmed working 1.4.0 GLES renderer.
- Open gameplay.log before graphics initialization and report the failing step/error if initialization fails.

Verified October 29, 2026: the user confirmed N64 multiplayer now works properly in 1.4.1, including the external-controller P1 / attached-Joy-Con P2 assignment fix. Version 1.4.1 was promoted to stable after that verification; the current stable release is 1.4.3.

# 1.4.0 - Nintendo 64 hardware-validation release

- Add integrated native Mupen64Plus-Next/GLideN64 gameplay with EGL/GLES3 video.
- Connect one, two or four independent native N64 controller ports using the saved controller profile.
- Add N64 engine routing, catalog metadata, package and corresponding source/notices.
- Preserve separate N64 control-stick/D-pad inputs; support analog control stick and C-stick.
- Probe JIT availability and use cached interpreter fallback when unavailable.
- Test actual N64 controller conversion, isolated four-player input and existing engine regressions.

N64 rendering, audio, performance and gameplay require physical Switch testing. The established 1.3.0 download and automatic engine catalog remain available pending validation.

# 1.3.0 - Four-player PlayStation



- Add four-controller pairing profiles for full controllers or four sideways Joy-Con.

- Route four independent input slots through PlayStation Multitap; disable unused virtual controllers.

- Enable Multitap automatically for four-player setups, with Port 1/Port 2 selection in the pause menu.

- Preserve working two-player profiles and pause when an active player disconnects.

- Validate the actual PCSX-ReARMed serial Multitap protocol and four-slot input isolation.



Two-player gameplay was confirmed by the user. Four-player gameplay requires Switch hardware testing.



# 1.2.0 — Local two-player controllers



- Add a shared two-player controller driver to the launcher and all gameplay engines.

- Add Plus > Controllers in the library and Controllers / player setup in the pause menu.

- Pair one sideways Joy-Con per player or two full controllers through the Switch controller applet.

- Rotate both single Joy-Con layouts, map Start/Select and shoulders, and provide a single Joy-Con pause chord.

- Route independent input to both emulated controller ports for NES, SNES, PlayStation and Genesis-family games.

- Clear disconnected input, pause on controller disconnect/layout changes, and suppress held input after pairing.

- Keep GB/GBA as single-handheld engines; link-cable emulation is not provided.

- Preserve login, existing game saves, RomM server independence and internal SD paths.



Host input and actual SNES two-port tests pass. Native/package validation is required; Switch controller hardware verification is pending.



# 1.1.2 — Author attribution



- Set the Homebrew Menu author to Monster Review for the launcher and every gameplay engine.

- Update GitHub and documentation author attribution.



# 1.1.1 — Rommulation branding



- Rename the app, Homebrew Menu titles, gameplay screens and public documentation to Rommulation.

- Add an original pixel-art CRT television and wired controller icon to the launcher and every engine executable.

- Preserve internal paths, engine ABI, saved login, downloads and saves.

- Retain the existing gameplay and automatic engine installer behavior.



# 1.1.0 - engine installation and additional consoles (publication pending)



- Detect missing engines when a downloaded game is launched. Resolve a compatible engine from a public catalog, download over HTTPS without RomM credentials, verify SHA-256/size/NRO signature, install on SD and continue launch.

- Keep downloaded engines for future launches; cancel/retry safely, preserve working files during replacement, and cache engine mappings for offline use.

- Add native NES/Famicom, Genesis/Mega Drive, Game Boy/Color and GBA components. These compile successfully; Switch hardware validation remains pending.

- Separate libraries and saves belonging to different RomM server addresses, retaining existing users' original cache and saved login.

- Add cartridge archive format selection, RTC saves, GBA save-size handling and disc/side switching when exposed by the engine.

- Include a public CA bundle and a release preparation script that binds the app to a real public engine catalog.



The automatic downloader is implemented but is not live in the unconfigured local build: engine packages must be published and the catalog address included at build time. N64 and Dreamcast graphics integration remains pending. This is not a claim that every RomM platform can be emulated.



# 1.0.0 - Rom NX release



- Rename the application and Homebrew Menu title to Rom NX.

- Remove the development banner and RomM / Switch heading; show the release version.

- Replace Find your next adventure with the selected console name.

- Retain the working 0.3.1 gameplay, downloads, artwork and console icons.

- Preserve internal SD paths, saved login, downloads and saves.



The user confirmed smooth SNES and PlayStation gameplay, launches and downloads in 0.3.1. This release changes branding and labels only. Native builds and executable/package validation passed.



# 0.3.1 - gameplay performance, scrolling artwork and console icons



- Remove per-sample audio-service polling; acquire/submit complete 1,024-frame buffers.

- Enable PCSX-ReARMed ARM64 dynamic recompilation with guarded interpreter fallback and a pause-menu CPU mode option.

- Reduce software framebuffer work and allow bounded catch-up presentation skips without dropping emulated audio.

- Add achieved/target FPS and core/display timing to the pause menu and gameplay.log.

- Load covers around the visible page as users scroll, including entries beyond the initial cache; prioritize launches/downloads and cancel obsolete art work.

- Replace long console-card labels with original bundled pixel-art console images and entry counts; keep the selected name in the heading.

- Preserve login, downloads and local game-save paths.



Native builds and host regressions passed. The previous 0.3.0 version was confirmed on Switch for SNES and PlayStation; these 0.3.1 changes still require hardware validation.



# 0.3.0 - integrated gameplay components



- Replace external RetroArch core discovery with bundled native SNES and PlayStation engines using the RomM NX frontend.

- Add gameplay video, stereo audio resampling, controller input, frame pacing and an in-game pause menu.

- Add local automatic battery/memory-card saves, manual save/load states, backup recovery and return to the library with saved login.

- Prepare ZIP games with size/checksum validation, confined relative paths, progress/cancellation and extraction caching.

- Download multi-file RomM entries as complete ZIPs so companion disc tracks stay together.

- Keep complete console pagination, title/all-entry views, downloads and automatic login.

- Include pinned upstream sources and their licenses. No RetroArch application, BIOS or games are bundled.



SNES core emulation smoke tests and shared host helper regressions passed on PC. All native components build and pass executable/package validation. Switch gameplay has not been tested. PlayStation uses the interpreter; performance and compatibility remain unverified. Other console engines are not bundled yet.



# 0.2.3 â€” complete console browsing and emulator guidance



- Automatically retrieve all pages rather than stopping browsing at 20 entries.

- Group same-title files/versions into one card; Y exposes every individual server entry.

- Show loaded server-entry count and selected filename.

- Browse while the collection/artwork loads; prioritize queued downloads after enumeration.

- Recognize alternative compatible RetroArch cores and platform aliases.

- Explain the one-time RetroArch Switch installation when no core is installed.

- Preserve automatic login and downloaded files.



Host regression tests and native build/package checks passed. New hardware validation is pending.



# 0.2.2 â€” automatic sign-in



- Save every successful login automatically; no remember-toggle required.

- Reuse saved sessions at startup and retry them without a new pairing code.

- Preserve sign-in through NRO updates and network failures.

- Save only server/access/refresh-token information, never username/password.

- Recover staged/backup sessions after interrupted writes.

- Minus explicitly clears every saved session copy; Plus exits while staying signed in.

- Keep the console/filter/pagination fixes from 0.2.1.



Direct tests of the actual session storage implementation passed. Native build/package validation passed; Switch restart testing is pending.



# 0.2.1 â€” console list and per-console games



- Stop hiding consoles with zero/missing counts.

- Use current platform_ids filtering with legacy platform_id compatibility.

- Parse and deduplicate by game ID; retain distinct same-title versions.

- Reject games whose platform ID differs from the selected console.

- Show the server's game total and improve page availability checks.

- Add count/ID diagnostics without credentials.



Direct tests of the app's shared C data parser passed with six consoles and 66 distinct games across four pages. Native compilation and NRO checks passed. Switch validation is pending.



# 0.2.0 â€” short-code pairing and password fallback



- Setup defaults to a short pairing code; no full-token typing.

- X switches to username/password without changing the server.

- Pairing accepts eight letters/digits, normalizes case and optional separators.

- Password login exchanges credentials for read-only access and refresh tokens.

- Passwords are not written to saved sessions or logs.

- Saved OAuth sessions refresh before their access token expires.

- Clear errors for invalid/expired codes, rate limiting, unsupported pairing and rejected passwords.

- Existing saved API-token sessions remain compatible.



Native build and NRO structural checks passed. Seventeen mock-fixture checks passed. New authentication flow has not yet been exercised on the Switch.

