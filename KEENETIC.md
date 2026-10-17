# Enigma ETP for Keenetic

Current Keenetic client: **1.1.11**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.11 restores faster recovery in automatic mode: QUIC is retried after 30 seconds rather than five minutes. In `auto-edge`, the direct path is retried after 30 seconds, then after one and two minutes if it remains unavailable. The single-probe and concurrent-switch protections remain. The ETP/1 protocol, profile format, server requirements and existing keys are unchanged.

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The updater fetches the latest full package, verifies its SHA-256, saves a backup and attempts rollback if installation or service checks fail. Updates may skip intermediate versions.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.11-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved.

SHA-256: `ce4f2c3cc5647d970431947a8582fd594c2731982f969bdb3e5b40ea40bc7c9f`
