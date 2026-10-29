# Genesis / Mega Drive regression evidence

**Hardware verification — October 29, 2026:** the user confirmed Genesis/Mega Drive ROMs work on Nintendo Switch in 1.4.3, including two-player gameplay. The startup crash fix is user-verified. This report does not establish every Sega title, Sega CD or every peripheral.

1.4.3 fixes a concrete frontend crash: the vendored Genesis Plus GX libretro adapter calls RETRO_ENVIRONMENT_SET_DISK_CONTROL_INTERFACE with NULL after loading a cartridge (a cartridge has no disc interface). The old Rommulation environment callback dereferenced it. A host test using the actual core and the actual environment function faults with process exit 3221225477 before the fix; the fixed function completes load and emulation.

The test builds the vendored core's portable cartridge path with Windows GCC, and extracts the production environment/save functions unchanged into its harness. Platform drawing and audio devices are replaced by validating/counting callbacks. Native Switch builds retain their original CD/CHD support; the host cartridge test omits CHD and uses the bundled zlib sources. No emulator CPU or cartridge-loader logic is mocked.

The original generated cartridge contains a Mega Drive header, reset vectors and a 68000 instruction sequence that writes a RAM marker and loops. Tests cover valid/empty basic and extended disc-interface registration, cartridge load, 120 emulated frames, video bounds, audio samples, two input ports, the CPU RAM marker, state serialization/restore, trimmed-SRAM reload, full SRAM writes and overwriting an erased save. No commercial game or proprietary BIOS is used or distributed.

Run tests/build_genesis_host.py with a host gcc.exe (the release test used official skeeto/w64devkit), then tests/run_genesis_runtime_tests.py with the matching g++.exe. The generated cartridge and build products stay under build/genesis-host and are excluded from release packages.

This validates a real cartridge-loading crash and core/host integration on PC. The subsequent user report confirms Genesis/Mega Drive gameplay and two-player mode on Switch. Detailed performance measurements, battery save/relaunch coverage, Sega CD/BIOS behavior and universal game compatibility are not established by that report. Startup progress and player/device assignments are in switch/romm_nx/gameplay.log if a further problem remains.
