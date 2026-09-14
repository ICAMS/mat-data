# Contributing

This repository holds only data (YAML material entries, JSON schemas, the
PROPS mapping table) and documentation — no code.

## Adding or updating a material entry

1. Copy `entries/template.yaml.example` to
   `entries/<stable-material-key>.yaml` (lowercase letters, digits,
   underscores only).
2. Fill in measured/calibrated values, following `schemas/material.schema.json`.
3. Open a pull request.

## What CI checks

`.github/workflows/validate.yml` checks out this repository together with
[mat-data-handler](https://github.com/ICAMS/mat-data-handler) (pinned to a
released tag) and runs its validator against `entries/` and `schemas/` here:

- every entry parses as YAML with no aliases, duplicate keys, or non-finite
  numbers,
- every entry validates against `schemas/material.schema.json`,
- (optional) the combined single-YAML collection builds successfully.

No validation logic lives in this repository — it is intentionally borrowed
from `mat-data-handler` so this repo stays data-only. If validation rules need
to change, that's a `mat-data-handler` change, not a `mat-data` change.

## Review

A maintainer reviews the physical plausibility of new/changed values —
passing CI only confirms the entry is well-formed and schema-valid, not that
the material data is physically correct.

## Releases

Once a set of PRs is merged, a maintainer tags a new release (CalVer, e.g.
`v2026.10.0`) so downstream consumers can pin to it.
