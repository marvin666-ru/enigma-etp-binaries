# Enigma ETP for Keenetic

Current Keenetic client: 1.1.3. The public repository contains only the compiled ARM64/MT7621 installation archive and `keenetic-release.json`; no client source, profile links, tokens or certificates are included.

For the first upgrade from an older client, download `Enigma-ETP-Keenetic-1.1.3-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `sh Enigma-ETP-Keenetic/install.sh`.

SHA-256: `b290a28521c98218ddcaf79ee3b3c6fe866bdc85777f957033fa7a0a349eb53b`

From 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. Profiles, keys and Keenetic routes are not replaced. The updater saves a backup and attempts rollback if installation or service checks fail.
