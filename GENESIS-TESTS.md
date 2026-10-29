# Genesis / Mega Drive regression evidence

1.4.3 fixes a concrete frontend crash: the vendored Genesis Plus GX libretro adapter calls RETRO_ENVIRONMENT_SET_DISK_CONTROL_INTERFACE with NULL after loading a cartridge (a cartridge has no disc interface). The old Rommulation environment callback dereferenced it. A host test using the actual core and the actual environment function faults with process exit 3221225477 before the fix; the fixed function completes load and emulation.

The test builds the vendored core's portable cartridge path with Windows GCC, and extracts the production environment/save functions unchanged into its harness. Platform drawing and audio devices are replaced by validating/counting callbacks. Native Switch builds retain their original CD/CHD support; the host cartridge test omits CHD and uses the bundled zlib sources. No emulator CPU or cartridge-loader logic is mocked.

The original generated cartridge contains a Mega Drive header, reset vectors and a 68000 instruction sequence that writes a RAM marker and loops. Tests cover valid/empty basic and extended disc-interface registration, cartridge load, 120 emulated frames, video bounds, audio samples, two input ports, the CPU RAM marker, state serialization/restore, trimmed-SRAM reload, full SRAM writes and overwriting an erased save. No commercial game or proprietary BIOS is used or distributed.

Run tests/build_genesis_host.py with a host gcc.exe (the release test used official skeeto/w64devkit), then tests/run_genesis_runtime_tests.py with the matching g++.exe. The generated cartridge and build products stay under build/genesis-host and are excluded from release packages.

This validates a real cartridge-loading crash and core/host integration on PC. It does not establish physical Switch performance, Sega CD/BIOS behavior, or universal game compatibility. Retest a Genesis game on Switch, including launching, input, audio/video, save/relaunch and returning to the library. Startup progress and player/device assignments are in switch/romm_nx/gameplay.log if a further problem remains.
