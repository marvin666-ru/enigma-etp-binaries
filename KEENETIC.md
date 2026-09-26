# Enigma ETP for Keenetic

Current Keenetic client: 1.1.3. The public repository contains only the compiled ARM64/MT7621 installation archive and `keenetic-release.json`; no client source, profile links, tokens or certificates are included.

For the first upgrade from an older client, download `Enigma-ETP-Keenetic-1.1.3-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `sh Enigma-ETP-Keenetic/install.sh`.

SHA-256: `2dea657ef310f487fe67d64476c49d322ff2b4986af3c31173b4a59db53a022b`

From 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. Profiles, keys and Keenetic routes are not replaced. The updater saves a backup and attempts rollback if installation or service checks fail.
