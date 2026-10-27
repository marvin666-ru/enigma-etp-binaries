# Enigma ETP for Keenetic

Current Keenetic client: **1.1.16**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.16 adds a progress bar for future client updates: archive download shows its measured percentage when the server provides a size, while verification and installation show the current stage. The "Use for Internet access" checkbox is removed from ETP Settings. Saving a profile no longer changes this routing option; existing routes remain unchanged. The faster VPS failover from 1.1.15 is retained. No server, Android, or macOS update is required. Profiles and keys are unchanged.

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The updater fetches the latest full package, verifies its SHA-256, saves a backup and attempts rollback if installation or service checks fail. Updates may skip intermediate versions.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.16-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved. The progress bar becomes visible after 1.1.16 is installed, so this particular upgrade still uses the previous update screen.

SHA-256: `4c0187254147ab5faef32ff59be4870c0f2ecf065a30b9f1887007d7a50a4a03`
