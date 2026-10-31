# Rommulation updates

## Important: check your Switch date and time

**Before signing in or using automatic updates, make sure the Switch's date, year and time match the current real-world date and time.** A clock set in the past or future can cause HTTPS certificate verification to fail, blocking both RomM sign-in/device pairing and GitHub updates.

Symptoms can include **“SSL peer certificate or SSH remote key was not OK”** during sign-in, or **“Update server unavailable”** at startup. The SSH wording is part of the network library's generic error; Rommulation connects over HTTPS.

1. Open **System Settings → System → Date and Time** on the Switch.
2. Check the year, date, time and time zone. Enable **Synchronize Clock via Internet** if available, or set the correct date and time manually.
3. Fully close and reopen Rommulation, then retry sign-in or the update check.

The clock needs to be correct; continuous internet clock synchronization is not required if you set it accurately yourself. The user confirmed that correcting the Switch clock resolved both failures on October 31, 2026. These messages can have other causes too, but check the clock first.

Starting with 1.5.0, automatic app updates are **ON by default**. Install the complete 1.5.0 ZIP once; older versions cannot install this updater themselves. Merge the switch folder into the SD root and replace included files. Keep your existing romm_nx folder: sign-in, downloads and saves remain.

## Turn automatic updates off

Press **ZL** on the library or sign-in screen to open **App updates**. Press **X** until **Automatic updates: OFF** appears, then **B** to return. The preference remains saved after restarting. Turning it off cancels an active update transfer and prevents automatic checks and installation. Browsing, downloads and gameplay continue normally.

With automatic updates off, press **A** in App updates to check and download manually, then **A** again to install and restart. Manual checks do not enable automatic updates. Press X to enable them again; startup checking resumes on the next launch.

## Safe installation and recovery

Enabled updates use GitHub's latest published stable release, HTTPS certificate validation, bounded downloads, SHA-256 and app identity/version checks. They download into an inactive slot. A verified update waits at the console menu for a five-second restart countdown. **B** postpones for this session. Games are never interrupted; gameplay runs in a separate engine process.

The previous app slot is retained. **Y** in App updates restores it and turns automatic updates off. The bootstrap can recover from a damaged selected slot or a failed startup before the first rendered frame. If the loader cannot restart, reopen Rommulation through Homebrew Menu. Reinstall the complete ZIP if neither slot is valid.

The bootstrap contains the hbmenu icon and stays unchanged during automatic app updates. Future icon/bootstrap changes require the complete installer. The update payload is RommulationApp.nro with update.txt; neither is a standalone installer. Gameplay engines use the release's verified engine catalog; installed engines are refreshed when needed for gameplay. No GitHub account is needed on the Switch.

Desktop recovery/network tests and native build validation do not replace physical Switch update/relaunch testing. The first Rommulation updater build still needs that test.
