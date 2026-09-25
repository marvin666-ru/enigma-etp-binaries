# Enigma ETP server installation

Current server core: **1.1.2**. This public repository contains compiled installation binaries only; server source is kept in the private `enigma-etp-core` repository. No live tokens, certificates, or profiles are included.

Download all three archive parts and reconstruct the package:

```bash
cat etp-turnkey-1.1.2.part-{aa,ab,ac} > etp-turnkey-1.1.2.tar.gz
echo "6fde67e1fedb3a331a2ecb62977ea9b8c707bbd7858cb5519fd077bb7e4a6c36  etp-turnkey-1.1.2.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.2.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles, and server settings:

```bash
sudo bash ./upgrade.sh
```

For a clean VPS only:

```bash
sudo bash ./install.sh --host SERVER_IP_OR_DNS --name "Enigma"
```

The package includes Linux `amd64` and `arm64` server binaries. The old 1.1.1 archive remains available for rollback.
