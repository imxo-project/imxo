# IMXO Research Plan

**Document status:** DRAFT  
**Created:** 2026-10-18  
**Updated:** 2026-10-18

This living document manages the IMXO research queue. It is not research evidence, a requirement, an architectural decision, or a separate `PLAN-*` artifact class. An `RSCH-xxxx` identifier exists only when the corresponding card exists under [`docs/en/research/`](../research/README.md).

The plan and the initial set of cards require Project Lead review and approval before substantive research begins. Every created card has `DRAFT` status; its facts, analysis, and conclusion sections remain unfilled.

## Goals of the current stage

- define verifiable boundaries for the first independent research tasks;
- address factual gaps identified by `USE-0001…USE-0004` and `Q-0001…Q-0014`;
- avoid selecting container, logical-model, trust, SDK, or conformance architecture;
- prepare parallel work without identifier or file conflicts.

## Created research cards

| ID | Topic | Priority | Status | Primary relationships | Phase and dependencies |
|---|---|---|---|---|---|
| [RSCH-0001](../research/RSCH-0001-container-architecture-comparison.md) | Container Architecture Comparison | P0 | `DRAFT` | Q-0001, Q-0002; USE-0001/0002/0003/0004 | Independent foundation research |
| [RSCH-0002](../research/RSCH-0002-safe-physical-file-updates.md) | Safe Physical File Updates | P0 | `DRAFT` | Q-0002, Q-0012, Q-0014; USE-0002/0004 | Parallel with RSCH-0001; reconcile findings later |
| [RSCH-0003](../research/RSCH-0003-text-layer-models.md) | Text Layer Models | P0 | `DRAFT` | Q-0003, Q-0006; USE-0001/0004 | Independent research |
| [RSCH-0004](../research/RSCH-0004-object-relationships-alternative-assertions.md) | Objects, Relationships, and Alternative Assertions | P0 | `DRAFT` | Q-0003, Q-0009, Q-0014; USE-0001/0002/0003/0004 | Independent survey; design later |
| [RSCH-0005](../research/RSCH-0005-provenance-transformation-chains.md) | Provenance and Transformation Chains | P0 | `DRAFT` | Q-0007, Q-0009; USE-0001/0002/0003/0004 | Parallel with RSCH-0004/0006 |
| [RSCH-0006](../research/RSCH-0006-integrity-consistency-trust-boundaries.md) | Integrity, Consistency, and Trust Boundaries | P0 | `DRAFT` | Q-0007, Q-0008, Q-0012; USE-0002/0003/0004 | Parallel with RSCH-0005 |
| [RSCH-0007](../research/RSCH-0007-structured-file-sanitization.md) | Structured File Sanitization | P0 | `DRAFT` | Q-0002, Q-0012, Q-0014; USE-0002/0004 | Separate from steganalysis; uses RSCH-0002 boundaries |
| [RSCH-0008](../research/RSCH-0008-media-steganography-steganalysis.md) | Media Steganography and Limits of Steganalysis | P1 | `DRAFT` | Q-0008, Q-0014; USE-0002 | Independent of structural sanitization |
| [RSCH-0009](../research/RSCH-0009-partial-representations-selective-extraction.md) | Partial Representations and Selective Extraction | P0 | `DRAFT` | Q-0003, Q-0011, Q-0012; USE-0003/0004 | Parallel with RSCH-0004; reconcile later |
| [RSCH-0010](../research/RSCH-0010-ai-ingestion-threats-semantic-laundering.md) | AI Ingestion Threats and Semantic Laundering | P1 | `DRAFT` | Q-0007, Q-0008, Q-0012; USE-0003 | Independent threat analysis |
| [RSCH-0011](../research/RSCH-0011-ai-input-efficiency-comparison.md) | AI Input Preparation Comparison | P1 | `DRAFT` | Q-0011, Q-0012; USE-0003 | Method first; physical measurements after a prototype |
| [RSCH-0012](../research/RSCH-0012-cv-annotation-interchange-formats.md) | CV Annotation Interchange Formats | P1 | `DRAFT` | Q-0003, Q-0009; USE-0001/0003/0004 | Independent; future USE cards are not treated as published |

## Topics without assigned RSCH identifiers

| Topic | Preliminary priority | Why it remains only in the plan | Entry condition |
|---|---|---|---|
| Accessibility standards, structural reading models, and conformance boundaries | P1/P2 | Factual research for Q-0013 starts after approval of the overall plan; future USE-0008 does not yet exist | Plan approval and clarification of boundaries between Q-0010 and Q-0013 |
| Long-term preservation and independent verification | P2 | The material operational profile of future USE-0006 has not been published | Creation of USE-0006 or a separate Project Lead decision to start earlier |
| Libraries, extension handling, compatibility profiles, and conformance suites | P1/P2 | The topic combines different methods and is currently too broad for one verifiable card | Results from RSCH-0001/0002/0004/0009 followed by division into concrete questions |

These rows do not reserve identifiers and are not research artifacts.

## Relationship to published USE-0004

[`USE-0004 — Editing a Structured Image While Preserving Representation Consistency`](../use-cases/USE-0004-structured-image-editing.md) is published as `DRAFT / CANDIDATE`. Ordinary fragment editing while preserving consistency is linked to existing `RSCH-0001`, `RSCH-0002`, `RSCH-0003`, `RSCH-0004`, `RSCH-0005`, `RSCH-0006`, `RSCH-0007`, `RSCH-0009`, and `RSCH-0012`. These links cover container constraints, text, moving and copying a whole object, cutting and moving part of one, copying a part, transforming a mask/bounding box/polygon, joining fragments, provenance, verification boundaries, sanitization as a separate boundary case, and operation by an editor that does not support some semantic annotations.

The research must distinguish structural recalculation of geometry from the need to revalidate meaning. Moving, copying, splitting, merging, and sanitization are not treated as one operation. No new research card or identifier is created for this preparation.

## Parallel work packages

### A. Container and safe storage

`RSCH-0001`, `RSCH-0002`, and `RSCH-0007`. The first two may proceed in parallel; sanitization findings are reconciled with them afterward. `RSCH-0008` remains a separate study of hidden channels.

### B. Semantics, text, and annotations

`RSCH-0003`, `RSCH-0004`, and `RSCH-0012` may proceed independently, followed by reconciliation of common terminology.

### C. Provenance, trust, and threats

`RSCH-0005`, `RSCH-0006`, and `RSCH-0010` proceed in parallel, but the final threat model must use verified provenance and trust boundaries rather than replace them.

### D. Partial and AI consumption

`RSCH-0009` and preparation of the `RSCH-0011` method may proceed in parallel. Experimental conclusions in RSCH-0011 require approved test materials; measurements of physical IMXO cost require a working prototype.

## Review and execution order

1. The Project Lead reviews the boundaries, priorities, and set of created cards.
2. After approval, individual researchers take specific `RSCH` files and record the source versions they use.
3. A card moves to `REVIEW` only after the actual research and self-checking against its completion criteria.
4. Verified findings return to the related `Q` cards; research does not make an `ADR` by itself.
5. The plan is updated to reflect actual state without reserving future identifiers.

## History

- 2026-10-28 — linked the plan to published USE-0004 and the updated set of existing research cards; research statuses were unchanged.

- 2026-10-18 — initial DRAFT plan, twelve initial research definitions, and three unnumbered later-queue topics created.
- 2026-10-18 — planned USE-0004 editing cases integrated into existing research definitions; English mirror created.
