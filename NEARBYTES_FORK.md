# Nearbytes Fork Notes

This repository is a Nearbytes-maintained fork of the upstream MEGAcmd project.

Upstream project:

- https://github.com/meganz/MEGAcmd

Upstream user downloads and primary documentation:

- https://mega.nz/cmd

## Why this fork exists

Nearbytes needs native remote-to-local sync support for incoming MEGA shares that do not have full access.

Upstream behavior historically required full access for syncs, which forced Nearbytes to fall back to repeated pull polling for recipient shares.

## Nearbytes-specific changes

This fork carries only the minimum Nearbytes-specific MEGAcmd surface changes:

- `sync --down`
- `sync --read-only`
- CLI wiring to request SDK `TYPE_DOWN`
- help text and command validation for that mode

The corresponding SDK behavior lives in the Nearbytes SDK fork:

- https://github.com/nearbytes/sdk

## What to read first

If you want normal MEGAcmd usage or build instructions, read the upstream-compatible documentation already present in this repository:

- [README.md](README.md)
- [UserGuide.md](UserGuide.md)

If you want only the Nearbytes-specific delta, read this file and the linked issue:

- https://github.com/nearbytes/MEGAcmd/issues/1

## Release policy

This fork should avoid copying and rewriting upstream docs.

Preferred maintenance model:

1. Keep upstream build and usage docs intact.
2. Keep this file short and limited to Nearbytes-specific behavior.
3. Publish binaries from this fork only when they differ materially from upstream.
4. Use release notes to describe the exact Nearbytes delta from upstream.