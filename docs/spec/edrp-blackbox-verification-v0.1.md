# EDRP Black-box Verification (v0.1)

## Summary
EDRP paid layers (decision kernel) remain private.  
Third parties can still verify **public formats** and **tamper-evident outputs**.

This document describes what is verifiable without revealing proprietary logic.

## What is publicly verifiable

### 1) Format alignment
- Receipt/Profile spec (public)
- in-toto Statement + DSSE envelope examples (public)

### 2) Artifact integrity (tamper-evident)
- Live outputs are published with `SHA256SUMS`
- Anyone can verify the published files match the hash manifest

### 3) Provenance linkage
- `RUN_INFO.json` links the published artifacts to a specific CI run:
  - repository
  - commit
  - GitHub Actions run URL

## Public references

### Intake / spec
- Receipt/Profile draft:
  https://github.com/edict-lab/edict-intake/blob/main/docs/spec/edrp-receipt-v0.1.md
- Examples (in-toto Statement + DSSE):
  https://github.com/edict-lab/edict-intake/tree/main/docs/spec/examples

### Live outputs
- Live outputs (latest):
  https://github.com/edict-lab/edict-sandbox/tree/main/docs/latest
- Hash manifest:
  https://github.com/edict-lab/edict-sandbox/blob/main/docs/latest/SHA256SUMS
- Run provenance:
  https://github.com/edict-lab/edict-sandbox/blob/main/docs/latest/RUN_INFO.json

### Demo (screenshots)
- Browser demo (screenshots):
  https://github.com/edict-lab/edict-intake/blob/main/docs/demo/docs/DEMO.md

## How to verify (quick)

### A) Verify integrity (SHA256SUMS)
Download `SHA256SUMS` and the artifacts you want to verify, then run:

sha256sum -c SHA256SUMS 

If you downloaded only some files:
sha256sum -c SHA256SUMS --ignore-missing

## Out of scope (private)

Decision algorithm / weights / tuning parameters

Proprietary policy logic in paid layers
