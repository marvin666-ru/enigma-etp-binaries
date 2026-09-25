# Enigma ETP server installation

Current server core: 1.1.3. This public repository contains compiled installation binaries only; server source is kept private. No live tokens, certificates or profiles are included.

Download the three `etp-turnkey-1.1.3.part-*` files in order and reconstruct the archive:

```sh
cat etp-turnkey-1.1.3.part-{aa,ab,ac} > etp-turnkey-1.1.3.tar.gz
echo '2c202b886dec672c570d5842304eb93996259a2bf382f271ed7c2c876df0647e  etp-turnkey-1.1.3.tar.gz' | sha256sum -c -
tar -xzf etp-turnkey-1.1.3.tar.gz
cd turnkey
sha256sum -c MANIFEST.sha256
```

To update an existing installation while preserving tokens, certificates, profiles and server settings:

```sh
sudo bash ./upgrade.sh
```

The package includes Linux amd64 and arm64 server binaries. Previous archives remain available for rollback.
