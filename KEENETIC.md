# Enigma ETP for Keenetic

Current Keenetic client: **1.1.15**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.15 speeds up the VPS health checks introduced in 1.1.14: both saved VPS profiles are probed every 15 seconds, and two consecutive materially better results can switch new sessions to the other VPS. The quality threshold remains 200 ms for the active VPS, at least twice the other VPS latency and at least 100 ms worse. Minimum dwell after a switch is one minute. Existing sessions are not moved; after restart the client starts with the primary VPS. Without a standby profile, behavior is unchanged. No server, Android, or macOS update is required. Profiles and keys are unchanged.

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The updater fetches the latest full package, verifies its SHA-256, saves a backup and attempts rollback if installation or service checks fail. Updates may skip intermediate versions.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.15-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved.

SHA-256: `50c2028d6a7270cc3579c3db50afbc3d5847d9d46e9bdc3f75c9f08e334983dc`
