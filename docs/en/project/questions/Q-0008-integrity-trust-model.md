# Q-0008. Integrity / Trust Model

**Status:** OPEN  
**Area:** Security / Trust  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

How should IMXO support integrity verification and represent trust state?

## Context

IMXO needs to represent integrity and trust state, including possible inconsistency between visible content and structured layers. Accidental corruption, visual/structured consistency, and trust in a source need to be distinguished. Specific mechanisms, including whether signatures are needed and what they cover, remain undefined.

## Scope

- hashing model and hash scope;
- relationship between visual and structured representations;
- indicators of modified or unverified data;
- user-facing trust indicator;
- partial verification rules;
- possible support for digital signatures;
- removal or recomputation of hashes and other verification data derived from sanitized content;
- consistency verification after a cascading change without an implicit requirement for a mandatory cryptographic model.

## Related research

- [RSCH-0006 — Integrity, Consistency, and Trust Boundaries](../../research/RSCH-0006-integrity-consistency-trust-boundaries.md)
- [RSCH-0008 — Media Steganography and Steganalysis](../../research/RSCH-0008-media-steganography-steganalysis.md)
- [RSCH-0010 — AI Ingestion Threats and Semantic Laundering](../../research/RSCH-0010-ai-ingestion-threats-semantic-laundering.md)

## Related requirements

None yet.

## Related design documents

- [USE-0003 — Structured Screenshot as Input to an AI System](../../use-cases/USE-0003-structured-screenshot-ai-input.md)
- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-10-18 — links to the initial DRAFT research cards added and later redirected to their English mirrors; status remains `OPEN`.

- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with verification of the sanitized result from USE-0002; status remains `OPEN`.
