# EDRP Receipt Profile for SLSA / in-toto (Draft v0.1)

## Scope
This document defines a minimal “receipt/profile” shape and mapping guidance for SLSA/in-toto style attestations.
It does NOT specify any decision algorithm/weights/tuning (out of scope / trade secret). Only inputs/outputs and verifiable references.

## Goal
- Standardize CI/CD evidence as a Receipt
- Produce reproducible verdict metadata (pass/fail/indeterminate) with reason codes
- Publish audit-ready outputs (reports/cards/checklists) + timepoint snapshot references

## Minimal fields (suggested)
- `schema_version`
- `timepoint` (when this receipt/verdict was computed)
- `subject` (artifact or release being judged)
- `inputs` (repo/ref/commit/build id; minimal pointers)
- `environment` (runner/ci; minimal)
- `evidence[]` (URIs to logs/materials/attestations; references only)
- `requested_outputs[]` (e.g., report/cards/checklist)
- `verdict` + `reason_codes[]` + `next_action` (decision vector)
- `outputs[]` (URIs to published artifacts)
- `snapshot` (timepoint snapshot URI; optional)

## Example (illustrative)
```json
{
  "predicateType": "https://example.org/edrp/receipt/v0.1",
  "subject": [
    { "name": "artifact-or-release", "digest": { "sha256": "..." } }
  ],
  "predicate": {
    "schema_version": "0.1",
    "timepoint": "2026-02-03T00:00:00Z",
    "inputs": { "repo": "org/repo", "ref": "refs/heads/main", "commit": "..." },
    "environment": { "ci": "github-actions", "runner": "ubuntu-latest" },
    "evidence": [
      { "type": "log", "uri": "https://example.org/logs/..." },
      { "type": "attestation", "uri": "https://example.org/attestations/..." }
    ],
    "requested_outputs": ["high_report", "cards", "checklist"],
    "decision": {
      "verdict": "pass",
      "reason_codes": ["example.reason.code"],
      "next_action": "allow"
    },
    "outputs": [
      { "name": "high_report.json", "uri": "https://github.com/edict-lab/edict-sandbox/blob/main/docs/latest/high_report.json" }
    ]
  }
}
