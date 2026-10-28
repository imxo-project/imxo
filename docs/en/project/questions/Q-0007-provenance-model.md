# Q-0007. Provenance Model

**Status:** OPEN  
**Area:** Provenance  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the normative IMXO provenance model be?

## Context

IMXO must support describing data origin and identifying who or what produced a specific part of the structured data. The exact model will be designed separately. Ordinary editing may create several derived fragments without turning provenance into a requirement to retain complete history or data removed through sanitization.

## Scope

- provenance structure and granularity;
- source identification;
- transformation chains;
- trusted and untrusted sources;
- provenance inheritance rules;
- interaction with hashes and signatures;
- provenance of derived fragments after copying, moving, splitting, and merging;
- distinction between a transformation chain and retention of complete image history;
- several fragments originating from one source without automatic confirmation of their current semantic classification;
- privacy and sanitization constraints: provenance must not require retention of prohibited old data;
- representing provenance of a removal or transformation without retaining the removed value;
- risk of disclosing removed content through provenance, derived identifiers, or hashes;
- recording that a transformation occurred without creating hidden history of the former content.

## Related research

- [RSCH-0005 — Provenance and Transformation Chains](../../research/RSCH-0005-provenance-transformation-chains.md)
- [RSCH-0006 — Integrity, Consistency, and Trust Boundaries](../../research/RSCH-0006-integrity-consistency-trust-boundaries.md)
- [RSCH-0010 — AI Ingestion Threats and Semantic Laundering](../../research/RSCH-0010-ai-ingestion-threats-semantic-laundering.md)

## Related requirements

None yet.

## Related design documents

- [USE-0003 — Structured Screenshot as Input to an AI System](../../use-cases/USE-0003-structured-screenshot-ai-input.md)
- [USE-0004 — Editing a Structured Image While Preserving Representation Consistency](../../use-cases/USE-0004-structured-image-editing.md)
- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-10-28 — backlink to published USE-0004 added; status remains `OPEN`.

- 2026-10-18 — links to the initial DRAFT research cards added and later redirected to their English mirrors; status remains `OPEN`.

- 2026-10-18 — scope expanded with provenance of derived fragments and the boundary between transformation chains and content history; status remains `OPEN`.
- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with the interaction between provenance and sanitization from USE-0002; status remains `OPEN`.
