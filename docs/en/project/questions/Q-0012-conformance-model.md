# Q-0012. Conformance Model

**Status:** OPEN  
**Area:** Conformance  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the normative IMXO conformance model be?

## Context

Conformance levels, mandatory implementation capabilities, and validation rules have not yet been defined. Planned USE-0004 adds future ordinary-editing test cases that must not be conflated with sanitization guarantees.

## Scope

- conformance levels;
- mandatory decoder and encoder capabilities;
- behavior for unknown extensions;
- test suites;
- reference files;
- validation rules;
- potential test cases for moving or copying an entire region;
- partial splitting of an annotated object, merging, overlapping, and cropping;
- loss of support for some annotations and reporting of unknown currency;
- distinction between ordinary editing and sanitization in future tests;
- no normative test matrix before research is complete and requirements are accepted;
- testable sanitization guarantees and cascade-change tests;
- behavior with unknown extensions and explicit reporting when the result cannot be guaranteed;
- fixtures containing residual structures, conflicting representations, and partially supported data;
- negative tests confirming that removed content does not remain in known dependent representations.

## Related research

- [RSCH-0002 — Safe Physical File Updates](../../research/RSCH-0002-safe-physical-file-updates.md)
- [RSCH-0006 — Integrity, Consistency, and Trust Boundaries](../../research/RSCH-0006-integrity-consistency-trust-boundaries.md)
- [RSCH-0007 — Structured File Sanitization](../../research/RSCH-0007-structured-file-sanitization.md)
- [RSCH-0009 — Partial Representations and Selective Extraction](../../research/RSCH-0009-partial-representations-selective-extraction.md)
- [RSCH-0010 — AI Ingestion Threats and Semantic Laundering](../../research/RSCH-0010-ai-ingestion-threats-semantic-laundering.md)
- [RSCH-0011 — AI Input Preparation Efficiency Comparison](../../research/RSCH-0011-ai-input-efficiency-comparison.md)

## Related requirements

None yet.

## Related design documents

- [USE-0003 — Structured Screenshot as Input to an AI System](../../use-cases/USE-0003-structured-screenshot-ai-input.md)
- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-10-18 — links to the initial DRAFT research cards added and later redirected to their English mirrors; status remains `OPEN`.

- 2026-10-18 — scope expanded with potential ordinary-editing test cases and their distinction from sanitization; status remains `OPEN`.
- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with testable sanitization properties from USE-0002; status remains `OPEN`.
