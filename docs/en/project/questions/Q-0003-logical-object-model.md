# Q-0003. Logical Object Model

**Status:** OPEN  
**Area:** Logical model  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the IMXO logical object model be?

## Context

The exact logical structure of IMXO has not yet been established. It must be defined after the foundational research and requirements refinement. Published [`USE-0004`](../../use-cases/USE-0004-structured-image-editing.md) adds editing cases in which a geometric region, object identity, and an assertion about that object may change differently.

## Scope

- base object types;
- mandatory and optional entities;
- relationships, identifiers, and references;
- data ownership and nesting;
- extension lifecycle;
- serialization of the logical model into the container;
- dependency types and the distinction between structural or semantic relationships and geometric proximity;
- parent-child relationships, derived representations, and alternative representations;
- multiple independent annotation sets with differing boundaries or categories;
- representation of a “stale after modification” state;
- distinction among a visual region, the identity of the described object, and an individual assertion about that object;
- representation of one semantic object by several disjoint regions and of one fragment by several descriptions;
- derived fragments and part-whole relationships without inferring semantic dependency from geometry alone;
- preservation or change of identity after copying, splitting, merging, and moving;
- distinction between a geometric transformation and semantic reclassification;
- open selection of identity rules, fields, and a relationship model without defining them prematurely;
- relationship between the logical model and cascade operations, while the specific safe-cascade algorithm remains within `Q-0014`.

## Related research

- [RSCH-0003 — Text Layer Models](../../research/RSCH-0003-text-layer-models.md)
- [RSCH-0004 — Object Relationships and Alternative Assertions](../../research/RSCH-0004-object-relationships-alternative-assertions.md)
- [RSCH-0009 — Partial Representations and Selective Extraction](../../research/RSCH-0009-partial-representations-selective-extraction.md)
- [RSCH-0012 — CV Annotation Interchange Formats](../../research/RSCH-0012-cv-annotation-interchange-formats.md)

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

- 2026-10-18 — scope expanded with object-identity and fragment-editing aspects in preparation for planned USE-0004; status remains `OPEN`.
- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with relationships and representations identified by USE-0002; status remains `OPEN`.
