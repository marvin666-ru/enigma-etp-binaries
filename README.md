# Enigma ETP server installation

Current server core: 1.1.7. This public repository contains compiled installation binaries and installation scripts only; server source is kept private. No live tokens, certificates or profiles are included.

Version 1.1.7 stops re-importing deleted Legacy profiles on every server restart. If the managed registry is missing, upgrade refuses to proceed rather than silently creating keys. The 1.1.6 metrics journal remains included. ETP/1, existing profiles, keys, and transport defaults are unchanged; Keenetic 1.1.5 and 1.1.6 remain compatible.

Download the three `etp-turnkey-1.1.7.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.7.part-{aa,ab,ac} > etp-turnkey-1.1.7.tar.gz
echo "13485726364eacf8c088724039abc9581031c1d8ff7ed69438bf5e7c812b3403  etp-turnkey-1.1.7.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.7.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and settings:

```sh
sudo bash ./upgrade.sh
```

The upgrade checks for an existing native profile registry, backs up both ETP and Edge binaries, checks both services, and restores the previous binaries if the health check fails. It also installs `enigma-etp-metrics.service`; logs are at `/var/log/enigma-etp/`. Existing tokens and certificates are untouched. The package includes Linux amd64 and arm64 binaries; previous archives remain available for rollback.
