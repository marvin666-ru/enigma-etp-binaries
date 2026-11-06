# Enigma ETP server installation

For the signed and notarized Apple Silicon WgTunnel client, see [MACOS.md](MACOS.md). For the Keenetic client, see [KEENETIC.md](KEENETIC.md).

Current server core: 1.1.11. This public repository contains compiled installation binaries and installation scripts only; server source is kept private. No live tokens, certificates or profiles are included.

Version 1.1.11 adds aggregate DNS lookup latency, total outbound TCP dial time, and UDP association destination-limit drops to the server diagnostics. The optional UDP/8443 listener from 1.1.10 remains available. ETP/1, profile format, keys and certificates are unchanged; existing Android and macOS clients remain compatible.

Download the three `etp-turnkey-1.1.11.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.11.part-{aa,ab,ac} > etp-turnkey-1.1.11.tar.gz
echo "4dabbf9b8c69ac44595aba5040ca9d7460b9cae8d9edb07df2beb60a97ca3352  etp-turnkey-1.1.11.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.11.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and settings:

```sh
sudo bash ./upgrade.sh
```

The upgrade checks for an existing native profile registry, backs up both ETP and Edge binaries and the server environment file, checks both services, and restores the previous state if the health check fails. It also installs `enigma-etp-metrics.service`; logs are at `/var/log/enigma-etp/`. Existing tokens and certificates are untouched. Open UDP/8443 in any provider firewall before using Keenetic 1.1.12. The package includes Linux amd64 and arm64 binaries; previous archives remain available for rollback.
