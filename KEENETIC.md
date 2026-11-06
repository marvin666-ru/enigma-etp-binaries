# Enigma ETP for Keenetic

Current Keenetic client: **1.1.17**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.17 adds aggregate session-opening latency, TLS/TCP slot-wait time, and host-wide UDP buffer error counters to the six-hour UTC diagnostic journal. The progress bar and routing controls from 1.1.16 remain unchanged. Profiles and keys are unchanged.

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The updater fetches the latest full package, verifies its SHA-256, saves a backup and attempts rollback if installation or service checks fail. Updates may skip intermediate versions.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.17-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved.

SHA-256: `97d2895ff6edccdd79a340f85dc6580ce231583b26f9be04cdb0d2be293452a4`
