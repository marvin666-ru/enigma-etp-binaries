# Enigma ETP for Keenetic

Current Keenetic client: 1.1.6. The public repository contains only the compiled ARM64/MT7621 installation archive and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.6 keeps the local SOCKS UDP association open after an upstream interruption and reconnects it with bounded retry intervals. It retains the 1.1.5 WAN route repair and update check. The ETP/1 format, profiles and keys are unchanged; server 1.1.7 remains compatible.

For a manual upgrade, download `Enigma-ETP-Keenetic-1.1.6-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `sh Enigma-ETP-Keenetic/install.sh`.

SHA-256: `75a04343048b0aa446cce14fe994d2ad6c80f37287eeaaf40bc16dad9fa27842`

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. Profiles, keys and Keenetic routes are not replaced. The updater saves a backup and attempts rollback if installation or service checks fail.
