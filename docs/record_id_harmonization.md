# Record ID Harmonization

This demo uses program-specific rules to avoid identifier clashes when harmonizing data.

## Source IDs
Both synthetic datasets use `record_id` values in the form `P1..P10000`.

## Standardized IDs
Each program applies a deterministic transformation that renames IDs into a non-overlapping namespace:

- RADx-UP: `PU` + 7-digit zero-padded number
  - Example: `P1` → `PU0000001`
- RADx-rad: `PR` + 7-digit zero-padded number
  - Example: `P1` → `PR0000001`

## Rules
These transformations are defined in:
- `rules/radx_up_rules.json`
- `rules/radx_rad_rules.json`

Each rule uses a sequence of regex substitutions to pad 1–7 digit identifiers.
