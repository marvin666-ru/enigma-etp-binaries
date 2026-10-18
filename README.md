# Enigma ETP server installation

For the signed and notarized Apple Silicon WgTunnel client, see [MACOS.md](MACOS.md). For the Keenetic client, see [KEENETIC.md](KEENETIC.md).

Current server core: 1.1.10. This public repository contains compiled installation binaries and installation scripts only; server source is kept private. No live tokens, certificates or profiles are included.

Version 1.1.10 adds an optional second ETP/1 QUIC listener on UDP/8443. The original UDP/TCP 443 and HTTP Edge 8444 endpoints, profile format, keys and certificates are unchanged. Existing Android and macOS clients remain compatible without updates. The upgrade enables UDP/8443 only when it is free and retains the 1.1.9 per-listener UDP diagnostics.

Download the three `etp-turnkey-1.1.10.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.10.part-{aa,ab,ac} > etp-turnkey-1.1.10.tar.gz
echo "1fce77bd5727848d8c5ff147bef613c0fd5fb7e3db660f169589f688f6a3b9fd  etp-turnkey-1.1.10.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.10.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and settings:

```sh
sudo bash ./upgrade.sh
```

The upgrade checks for an existing native profile registry, backs up both ETP and Edge binaries and the server environment file, checks both services, and restores the previous state if the health check fails. It also installs `enigma-etp-metrics.service`; logs are at `/var/log/enigma-etp/`. Existing tokens and certificates are untouched. Open UDP/8443 in any provider firewall before using Keenetic 1.1.12. The package includes Linux amd64 and arm64 binaries; previous archives remain available for rollback.
