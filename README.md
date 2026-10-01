# Enigma ETP server installation

Current server core: 1.1.6. This public repository contains compiled installation binaries and installation scripts only; server source is kept private. No live tokens, certificates or profiles are included.

Version 1.1.6 adds a separate metrics-journal service. It samples local aggregate metrics every ten seconds, rotates files in six-hour UTC buckets, retains up to 14 days, and limits diagnostic files to roughly 500 MiB. It does not change the ETP/1 wire protocol, profiles, keys, or transport-selection defaults. Keenetic 1.1.5 remains compatible.

Download the three `etp-turnkey-1.1.6.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.6.part-{aa,ab,ac} > etp-turnkey-1.1.6.tar.gz
echo "c0c93ffd785de82a0c949070f7166bd36c584bf653194322a21bb90b506d3ba7  etp-turnkey-1.1.6.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.6.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and settings:

```sh
sudo bash ./upgrade.sh
```

The upgrade backs up both ETP and Edge binaries, checks both services, and restores the previous binaries if the health check fails. It also installs `enigma-etp-metrics.service`; logs are at `/var/log/enigma-etp/`. Existing tokens and certificates are untouched. The package includes Linux amd64 and arm64 binaries; previous archives remain available for rollback.
