# EDRP Black-box Verification (v0.1)

## Goal
Verify EDRP results **without revealing the proprietary decision kernel**.

We discuss:
- public input/output formats
- verifiable outputs (hashes / optional signatures)
- provenance/attestation envelope formats (in-toto / DSSE)

Decision algorithm/weights/tuning are out of scope.

## What a verifier should check
1) **Input identity**
- Receipt/profile version and referenced evidence pointers (URIs)
- (Optional) receipt hash

2) **Output integrity**
- Published outputs (reports/cards/checklists)
- A **SHA256SUMS** file for all published artifacts (tamper-evident)

3) **Optional authenticity (stronger)**
- A DSSE-signed attestation or signature over the output manifest
- (Future) TEE-based attestation can strengthen “this code ran in a trusted environment”

## Current public references
- Live outputs (latest):
  https://github.com/edict-lab/edict-sandbox/tree/main/docs/latest
- Receipt/Profile draft:
  https://github.com/edict-lab/edict-intake/blob/main/docs/spec/edrp-receipt-v0.1.md
- Examples (in-toto Statement + DSSE):
  https://github.com/edict-lab/edict-intake/tree/main/docs/spec/examples
