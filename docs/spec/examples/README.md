# EDRP Attestation Examples (v0.1)

This folder contains **public examples** for mapping EDRP receipt/profile to in-toto / DSSE formats.
Paid/proprietary decision kernel remains private (out of scope).

## Spec (public)
- Receipt/Profile draft:
  https://github.com/edict-lab/edict-intake/blob/main/docs/spec/edrp-receipt-v0.1.md

## Examples (public)
- in-toto Statement example:
  edrp-receipt-statement.v0.1.json
- DSSE envelope example (placeholder signature):
  edrp-receipt-dsse.v0.1.json

## Notes
- `signatures[].sig` is intentionally empty (format example only).
- These examples focus on **inputs/outputs formats**, not the decision algorithm.
