# veirox-scoop — Scoop bucket (Windows)

> **DO NOT hand-edit the manifest.** It is auto-pushed by GoReleaser
> on every CLI release tag from `veirox-cloud/veirox-cli`.

## Repo purpose

Scoop bucket for the [Veirox CLI](https://veirox.com/cli.html)
on Windows.

## Why this repo is public

Scoop buckets are conventionally public — `scoop bucket add` clones
the repo unauthenticated. The CLI source itself stays private at
`veirox-cloud/veirox-cli`.

## Install (end-user)

```powershell
scoop bucket add veirox https://github.com/veirox-cloud/veirox-scoop
scoop install veirox
```

## How releases work

Same pipeline as `homebrew-veirox`: GoReleaser pushes the manifest
to this repo via the `SCOOP_BUCKET_TOKEN` PAT on every CLI tag. See
[`veirox-cli/.goreleaser.yaml`](https://github.com/veirox-cloud/veirox-cli/blob/main/.goreleaser.yaml)
`scoops:` block.

## What lives here

- `bucket/veirox.json` — the auto-generated Scoop manifest.
- `LICENSE` — Apache 2.0.
- `NOTICE`, `README.md`.

## If something breaks

1. Verify GoReleaser pushed (recent `goreleaserbot` commit in log).
2. Verify the CLI release uploaded Windows binaries.
3. SHA-256 checksums in the manifest must match — GoReleaser handles
   this; rerun the release workflow if drift detected.

## License

Apache 2.0.
