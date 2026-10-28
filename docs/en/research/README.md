# IMXO Research

This directory contains `RSCH` cards: verifiable research into existing standards, formats, technologies, and practices. An `RSCH` separates verified facts from analysis and may provide a recommendation, but it does not make an IMXO architectural decision.

Current priorities, dependencies, and topics without assigned identifiers are maintained in [`research-plan.md`](../project/research-plan.md). The registry below lists only cards that actually exist.

## Registry

| ID | Title | Status | Area | Related Q/USE | Phase/dependencies |
|---|---|---|---|---|---|
| [RSCH-0001](RSCH-0001-container-architecture-comparison.md) | Container Architecture Comparison | `DRAFT` | Container / Physical model | Q-0001/0002; USE-0001/0002/0003/0004 | Independent foundation |
| [RSCH-0002](RSCH-0002-safe-physical-file-updates.md) | Safe Physical File Updates | `DRAFT` | Storage / Recovery / Safety | Q-0002/0012/0014; USE-0002/0004 | Parallel with 0001 |
| [RSCH-0003](RSCH-0003-text-layer-models.md) | Text Layer Models | `DRAFT` | Text / Representation | Q-0003/0006; USE-0001/0004 | Independent |
| [RSCH-0004](RSCH-0004-object-relationships-alternative-assertions.md) | Objects, Relationships, and Alternative Assertions | `DRAFT` | Logical model / Semantics | Q-0003/0009/0014; USE-0001/0002/0003/0004 | Survey before design |
| [RSCH-0005](RSCH-0005-provenance-transformation-chains.md) | Provenance and Transformation Chains | `DRAFT` | Provenance | Q-0007/0009; USE-0001/0002/0003/0004 | Parallel with 0004/0006 |
| [RSCH-0006](RSCH-0006-integrity-consistency-trust-boundaries.md) | Integrity, Consistency, and Trust Boundaries | `DRAFT` | Integrity / Trust | Q-0007/0008/0012; USE-0002/0003/0004 | Parallel with 0005 |
| [RSCH-0007](RSCH-0007-structured-file-sanitization.md) | Structured File Sanitization | `DRAFT` | Privacy / Sanitization | Q-0002/0012/0014; USE-0002/0004 | Separate from 0008 |
| [RSCH-0008](RSCH-0008-media-steganography-steganalysis.md) | Media Steganography and Limits of Steganalysis | `DRAFT` | Security / Media | Q-0008/0014; USE-0002 | Independent |
| [RSCH-0009](RSCH-0009-partial-representations-selective-extraction.md) | Partial Representations and Selective Extraction | `DRAFT` | Logical model / Processing | Q-0003/0011/0012; USE-0003/0004 | Parallel with 0004 |
| [RSCH-0010](RSCH-0010-ai-ingestion-threats-semantic-laundering.md) | AI Ingestion Threats and Semantic Laundering | `DRAFT` | Security / AI consumption | Q-0007/0008/0012; USE-0003 | Independent threat analysis |
| [RSCH-0011](RSCH-0011-ai-input-efficiency-comparison.md) | AI Input Preparation Comparison | `DRAFT` | AI / Evaluation | Q-0011/0012; USE-0003 | Method before experiment |
| [RSCH-0012](RSCH-0012-cv-annotation-interchange-formats.md) | CV Annotation Interchange Formats | `DRAFT` | Annotations / CV | Q-0003/0009; USE-0001/0003/0004 | Independent |

Published [`USE-0004`](../use-cases/USE-0004-structured-image-editing.md) is linked to the existing research cards relevant to ordinary structured-image editing. No new research card or identifier was created for that publication.

## Package status

The cards are research definitions awaiting review of the overall plan. Substantive research has not begun; the Established Facts, Analysis, and Conclusion sections remain unfilled.
