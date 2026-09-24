# Enigma ETP server installation

Current server core: **1.1.1**.

The universal `auto-edge` profile uses this fallback order:

1. direct QUIC;
2. direct multiplexed TLS/TCP;
3. Edge HTTP/3;
4. Edge HTTP/2.

Reconstruct the installation archive:

```bash
cat etp-turnkey-1.1.1.part-{aa,ab,ac} > etp-turnkey-1.1.1.tar.gz
echo "1edce97545c018ff1747756aead0f52af32090d1526eb62e8531d8c2551fe614  etp-turnkey-1.1.1.tar.gz" | sha256sum -c -
tar -xzf etp-turnkey-1.1.1.tar.gz
cd turnkey
sudo ./install.sh --host SERVER_IP_OR_DNS --name "Enigma"
```

The archive contains Linux `amd64` and `arm64` binaries. Access tokens and
certificates are generated locally on the server and are not stored here.
