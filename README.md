# Enigma ETP server installation

Current server core: 1.1.5. This public repository contains compiled installation binaries only; server source is kept private. No live tokens, certificates or profiles are included.

Version 1.1.5 adds server-side outbound-dial timing and in-flight metrics. It does not change the ETP/1 wire protocol, profiles, keys, or transport-selection defaults. Existing router clients remain compatible. This is a diagnostics and route-repair release, not QUIC DATAGRAM/ETP/2.

Download the three `etp-turnkey-1.1.5.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.5.part-{aa,ab,ac} > etp-turnkey-1.1.5.tar.gz
echo "558971fee5c44555f6a68fb67c8a3c426061df679a070edd05f5cc7e249e8655  etp-turnkey-1.1.5.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.5.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and settings:

```sh
sudo bash ./upgrade.sh
```

The upgrade backs up both ETP and Edge binaries, checks both services, and restores the previous binaries if the health check fails. Outbound dial metrics are available at `127.0.0.1:9090/metrics`. The package includes Linux amd64 and arm64 binaries; previous archives remain available for rollback.
