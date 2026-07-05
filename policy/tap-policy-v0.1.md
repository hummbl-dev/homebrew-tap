# Tap Policy v0.1

## Purpose

`homebrew-tap` is a **downstream generated surface** from
[`hummbl-dev/packages`](https://github.com/hummbl-dev/packages). It exists solely
to publish Homebrew formulas derived from canonical package metadata and release
artifact receipts maintained in the upstream `packages` repository.

## Generation posture

- Formulas in this repository are **generated**, not hand-authored.
- The source of truth for package identity, versioning, licensing, and artifact
  locations is the `packages` repository.
- This repository holds **no independent artifact identity**. It does not host,
  version, or sign binaries. It only translates upstream metadata into the
  Homebrew formula format.

## Formula generation contract

Each generated formula must derive its core fields from `packages/index` and the
matching release artifact receipt:

| Formula field | Source |
|---------------|--------|
| `version`     | `packages/index` release version |
| `url`         | release artifact receipt `artifactUrl` |
| `sha256`      | release artifact receipt `sha256` |
| `license`     | `packages/index` package license |
| `homepage`    | `packages/index` package homepage |

See [`generated-formula-contract-v0.1.md`](./generated-formula-contract-v0.1.md)
for the full field mapping and validation rules.

## Non-canon posture

This repository is **non-canon**. Any discrepancy between a formula here and the
upstream `packages` metadata is a generation bug, not a source of truth. When in
doubt, `packages` wins. Edits made directly in this repository will be
overwritten on the next generation cycle.
