# Enigma ETP for Keenetic

Current Keenetic client: 1.1.4. The public repository contains only the compiled ARM64/MT7621 installation archive and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.4 writes the actual selected transport (H2, H3, QUIC or TCP) to the client log when it changes. The profile format, keys and router routes are unchanged.

For a manual upgrade, download `Enigma-ETP-Keenetic-1.1.4-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `sh Enigma-ETP-Keenetic/install.sh`.

SHA-256: `d9bc8c44b7400c39cb7f30de8067f0bde7ca4b9b3e0870d0925d2d098eadc9b9`

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. Profiles, keys and Keenetic routes are not replaced. The updater saves a backup and attempts rollback if installation or service checks fail.
