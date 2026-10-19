# Enigma ETP for Keenetic

Current Keenetic client: **1.1.13**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.13 lets the Keenetic client use a second saved ETP profile as a standby VPS. On a transport failure while opening a new TCP session or UDP association, the client probes the other VPS and switches after a successful response. Existing connections may break. It does not load-balance traffic across both VPS or automatically switch back while running; after restart it starts with the primary VPS. Without a standby profile, behavior is unchanged. No server, Android, or macOS update is required for this feature. Both VPS must already have valid ETP profiles. The 1.1.12 alternate QUIC port feature is retained.

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The updater fetches the latest full package, verifies its SHA-256, saves a backup and attempts rollback if installation or service checks fail. Updates may skip intermediate versions.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.13-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved.

SHA-256: `28e615b018d3fa63b6e09702d676498b3715434a5210aa33264d121ced8ca69a`
