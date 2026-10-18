# Enigma ETP for Keenetic

Current Keenetic client: **1.1.12**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.12 tries alternate QUIC on UDP/8443 when the profile's primary QUIC port fails, before the existing TCP/Edge fallback. A healthy selected port remains in use to avoid oscillation. Update the server to 1.1.10 first. The ETP/1 protocol, profile format and existing keys are unchanged; Android and macOS clients do not need updates.

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The updater fetches the latest full package, verifies its SHA-256, saves a backup and attempts rollback if installation or service checks fail. Updates may skip intermediate versions.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.12-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved.

SHA-256: `017a07a686d098aff768061a4211e07078173efef437344d077570fdf0297f9c`
