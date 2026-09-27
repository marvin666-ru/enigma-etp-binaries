# Enigma ETP server installation

Current server core: 1.1.4. This public repository contains compiled installation binaries only; server source is kept private. No live tokens, certificates or profiles are included.

Version 1.1.4 corrects the client-address label in TCP dial-failure logs and adds separate H2/H3 Edge counters. It does not change the wire protocol, profiles, keys, or transport-selection defaults. Existing router clients remain compatible.

Download the three `etp-turnkey-1.1.4.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.4.part-{aa,ab,ac} > etp-turnkey-1.1.4.tar.gz
echo "0c438916533a7af45ad19844552932de321cc592795e98bb18a88733c21d5970  etp-turnkey-1.1.4.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.4.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and settings:

```sh
sudo bash ./upgrade.sh
```

The upgrade backs up both ETP and Edge binaries, checks both services, and restores the previous binaries if the health check fails. H2/H3 counters are available from the existing loopback Edge metrics endpoint. The package includes Linux amd64 and arm64 binaries; previous archives remain available for rollback.
