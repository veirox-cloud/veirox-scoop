# veirox-scoop — Scoop bucket (Windows)

> **DO NOT hand-edit the manifest.** It is auto-pushed by GoReleaser
> on every CLI release tag from `veirox-cloud/veirox-cli`.

`AGENTS.md` in this directory is a symlink to this file: Claude Code, Codex, Copilot and every other agent read the identical text, so edit `CLAUDE.md` only and never keep a separate copy.

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

- `veirox.json` — the auto-generated Scoop manifest (ONE file, at repo
  root — `veirox-cli/.goreleaser.yaml`'s `scoops:` block sets no
  `folder:`, so GoReleaser writes it to the root, not `bucket/`).
- `CHANGELOG.md` — Keep-a-Changelog style; only worth updating for a
  real behavioral change to this bucket, not every manifest bump.
- `LICENSE` — Apache 2.0.
- `NOTICE`, `README.md`.

## If something breaks

1. Verify GoReleaser pushed (recent `goreleaserbot` commit in log).
2. Verify the CLI release uploaded Windows binaries.
3. SHA-256 checksums in the manifest must match — GoReleaser handles
   this; rerun the release workflow if drift detected.

## License

Apache 2.0.
