# Generated Formula Contract v0.1

## Input

Formula generation consumes two artifacts from
[`hummbl-dev/packages`](https://github.com/hummbl-dev/packages):

1. **Package identity registry** (`packages/index`) — declares the canonical
   package identity, license, and homepage for each publishable tool.
2. **Release artifact receipt** — emitted per release, declares the concrete
   `version`, `artifactUrl`, and `sha256` of the published artifact.

## Output

A Homebrew `Formula` class with **deterministic fields**. Given identical inputs,
generation must produce a byte-identical formula file.

## Field mapping

| Receipt / registry field | Formula field | Notes |
|--------------------------|---------------|-------|
| `packageId`              | class name + file name | PascalCased for class, kebab-case for filename |
| `version`                | `version`     | exact string from receipt |
| `artifactUrl`            | `url`         | exact URL from receipt |
| `sha256`                 | `sha256`      | exact digest from receipt |
| `license`                | `license`     | SPDX identifier from identity registry |
| `homepage`               | `homepage`    | from identity registry |
| `desc`                   | `desc`        | short description from identity registry |

## Validation

Before a generated formula is accepted into this repository it must pass
validation:

- Every field listed above **must match the receipt fields exactly**.
- `version`, `url`, and `sha256` must be non-empty and equal to the receipt
  values byte-for-byte.
- `license` must be a valid SPDX identifier present in the identity registry.
- The formula must not introduce fields that have no upstream source (no
  hand-added dependencies, patches, or resources unless declared in `packages`).

A formula that fails validation is rejected and must not be committed.
