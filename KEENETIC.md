# Enigma ETP for Keenetic

Current Keenetic client: 1.1.7. The public repository contains only the compiled ARM64/MT7621 installation archive and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.7 adds a Settings button to download the last 24 hours of allowlisted ETP, Web API, and NDW4 logs as a ZIP. Profiles and keys are excluded; ETP links and labeled secrets are redacted. Review IP addresses and hostnames before sharing. The 1.1.6 UDP recovery and 1.1.5 WAN route repair remain included. The ETP/1 format, profiles and keys are unchanged; server 1.1.7 remains compatible.

For a manual upgrade, download `Enigma-ETP-Keenetic-1.1.7-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `sh Enigma-ETP-Keenetic/install.sh`.

SHA-256: `03d7772611b7ffc2dd764ba40361d2af62a35e1890beb204e8d8181eefa26317`

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. Profiles, keys and Keenetic routes are not replaced. The updater saves a backup and attempts rollback if installation or service checks fail.
