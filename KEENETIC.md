# Enigma ETP for Keenetic

Current Keenetic client: 1.1.5. The public repository contains only the compiled ARM64/MT7621 installation archive and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.5 checks and repairs the physical routes to the direct ETP server and HTTP Edge after a WAN change. Settings now checks GitHub for an available update when opened. The ETP/1 format, profiles and keys are unchanged.

For a manual upgrade, download `Enigma-ETP-Keenetic-1.1.5-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `sh Enigma-ETP-Keenetic/install.sh`.

SHA-256: `170bfe3dd309c66899beecea81fbb568106321db496300ae442e8b65be2527a4`

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. Profiles, keys and Keenetic routes are not replaced. The updater saves a backup and attempts rollback if installation or service checks fail.
