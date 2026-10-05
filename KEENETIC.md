# Enigma ETP for Keenetic

Current Keenetic client: **1.1.8**. This public repository contains the compiled ARM64/MT7621 installer and `keenetic-release.json`; source is kept in the private core repository. No profile links, tokens or certificates are included.

Version 1.1.8 fixes the first start on KeeneticOS 5.1.6 / Ultra KN-1811: the native `ndmc` is invoked without inherited Entware library paths, including for Web UI status. Startup locking no longer depends on BusyBox `stat`; a stale lock from a failed attempt is reclaimed. Clean install creates the Web API token with BusyBox-compatible tools. The 1.1.7 diagnostic log download, 1.1.6 UDP recovery and 1.1.5 WAN route repair remain included. The ETP/1 protocol, profile format and existing keys are unchanged; server 1.1.7 remains compatible.

For a manual installation or upgrade, download `Enigma-ETP-Keenetic-1.1.8-arm64-mt7621.zip`, verify its SHA-256, unpack it on the router's OPKG volume and run `./Enigma-ETP-Keenetic/install.sh install`. Existing profiles, Web API token and routes are preserved.

SHA-256: `9c1703bfee2a3e8a409e7048ae21cc747016bb4d5abeaf9a94addb212c4dcd49`

From client 1.1.3 onward, use **Enigma ETP → Settings → Check for update** in the Keenetic web interface. The client fetches the latest full package and verifies its SHA-256, so updates may skip intermediate versions. The updater saves a backup and attempts rollback if installation or service checks fail.
