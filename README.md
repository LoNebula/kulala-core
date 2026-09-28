# kulala-core (LoNebula rebuild mirror)

Rebuilt binaries of [kulala-core](https://github.com/andycowan/kulala-core) — the recovery fork of the original `mistweaverco/kulala-core` (which went private on 2026-09-27).

- **Source**: andycowan/kulala-core (recovery fork, MIT — see LICENSE)
- **Version**: `0.37.0-andycowan.1` (release tag: `v0.37.0-andycowan.1`, must match `kulala.nvim`'s `BACKEND_VERSION`)
- **Built with**: `bun run build:<target>` for all 5 targets (linux-x64/arm64, darwin-x64/arm64, windows-x64) on Ubuntu 26.04 / bun 1.4.0

## Rebuild

```sh
git clone https://github.com/andycowan/kulala-core && cd kulala-core
bun install
for t in linux-x64 linux-arm64 darwin-x64 darwin-arm64 windows-x64; do
  bun run build:$t
done
gh release create v0.37.0-andycowan.1 packages/core/dist/kulala-core-* \
  --title "kulala-core 0.37.0-andycowan.1 (all platforms)"
```

Used by `kulala.nvim` via `download_url = "https://github.com/LoNebula/kulala-core/releases/download/%s/%s"`.
