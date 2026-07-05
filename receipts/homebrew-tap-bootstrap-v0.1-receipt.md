# Receipt: homebrew-tap bootstrap v0.1

- **Repo:** hummbl-dev/homebrew-tap
- **Branch:** feat/devin/bootstrap-policy
- **Date:** 2025-07-04
- **Scope:** Bootstrap tap policy and generated-formula contract; add placeholder formula structure.

## Artifacts produced

| Path | Purpose |
|------|---------|
| `policy/tap-policy-v0.1.md` | Tap policy: downstream generated surface, non-canon posture |
| `policy/generated-formula-contract-v0.1.md` | Formula generation contract: input, field mapping, validation |
| `Formula/placeholder-hummbl.rb` | Placeholder formula (DRAFT, not for use) |
| `receipts/homebrew-tap-bootstrap-v0.1-receipt.md` | This receipt |

## Issues addressed

- #1 — Bootstrap tap policy and generated-formula contract
- #2 — Add placeholder formula structure for hummbl (draft pattern only)

## Notes

- No artifacts are published. The placeholder formula carries version
  `0.0.0-placeholder` and intentionally omits `url`, `sha256`, and `license`
  pending the first real release artifact receipt from `hummbl-dev/packages`.
- This receipt documents the bootstrap only; it is not a release receipt.
