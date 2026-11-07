# asad

asad is the node daemon for **Asa**. It embeds upstream [sing-box](https://github.com/SagerNet/sing-box) as a library (no fork, no `replace`) and serves multi-user **Shadowsocks 2022** and **AnyTLS** inbounds, talking to the Asa panel over a signed API (per-node Ed25519 identity, timestamp + nonce on every request).

This repository only hosts release binaries. Source lives in the private Asa repository.

## Install

```bash
ARCH=amd64   # or arm64
curl -fL -o /usr/local/bin/asad https://github.com/missuo/asad/releases/latest/download/asad-linux-$ARCH
chmod 0755 /usr/local/bin/asad
asad enroll --panel https://<your-panel> --node-id <id> --code <one-time code from the admin console>
asad install     # installs and starts the hardened systemd unit
asad status
```

Verify downloads against `SHA256SUMS` in each release.
