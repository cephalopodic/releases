# Cephalopodic Releases

This repository is the public binary release surface for Cephalopodic tools.

Its product role is distribution, not implementation. The source repositories
produce the binaries; this repository hosts the published release tags and
attached archives that downstream installers and operators consume. Other repos
such as the public Homebrew tap depend on this one being correct and stable.

## Product Surface

Release tags are tool-scoped so multiple Cephalopodic binaries can coexist
without version collisions:

- `cephi-v<version>`
- `fortress-v<version>`
- `scath-v<version>`

Published assets follow a uniform pattern:

- `<tool>-<version>-aarch64-apple-darwin.tar.gz`
- `<tool>-<version>-x86_64-apple-darwin.tar.gz`
- `<tool>-<version>-x86_64-unknown-linux-gnu.tar.gz`
- matching `.sha256` files for each archive

This repo should be the stable public fetch target for install surfaces rather
than a place to track plans, release notes, or implementation detail.

## Developer / Agent Notes

Treat the GitHub releases and attached asset set as the authoritative content
of this repo.

When operating here:

- Keep tag names tool-scoped.
- Upload archives and checksum files together.
- Preserve the asset naming convention because external installers depend on
  it.
- Do not move source, build, or packaging instructions into this repo; keep
  those in the implementation repos and let this repo stay distribution-only.

If a release pipeline or formula references a missing asset here, the fix
belongs in the release publication flow, not in runtime code.
