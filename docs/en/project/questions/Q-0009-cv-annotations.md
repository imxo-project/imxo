# Q-0009. Computer Vision Annotations

**Status:** OPEN  
**Area:** Annotations / CV  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

How should IMXO represent computer vision annotations and map external schemas?

## Context

IMXO must support multiple annotation sets from different sources. The boundary between normative IMXO concepts and mappings from external systems must be defined. Ordinary editing may preserve calculable geometry while making the former semantic classification of a fragment unverified or inapplicable.

## Scope

- compatibility with YOLO and COCO;
- bounding boxes, polygons, masks, and points;
- labels and confidence values;
- additional object properties;
- normative IMXO concepts;
- mappings from external schemas;
- independent annotation sets with differing boundaries, categories, and sources;
- coexistence of human and machine assertions without selecting a single “truth”;
- designation of annotations that became stale after an image change;
- consequences of moving or copying an entire annotated object;
- partial editing of a mask, polygon, or bounding box, including splitting, cropping, and joining fragments;
- geometric applicability of an annotation separately from its semantic currency;
- differing annotation resolutions and sources when geometry is transformed;
- prohibition on automatically transferring the original classification to every resulting fragment without new grounds;
- an explicit unknown-currency state after operations, without requiring IMXO itself to perform recognition again;
- removal or update of related annotations during sanitization.

## Related research

- [RSCH-0004 — Object Relationships and Alternative Assertions](../../research/RSCH-0004-object-relationships-alternative-assertions.md)
- [RSCH-0005 — Provenance and Transformation Chains](../../research/RSCH-0005-provenance-transformation-chains.md)
- [RSCH-0012 — CV Annotation Interchange Formats](../../research/RSCH-0012-cv-annotation-interchange-formats.md)

## Related requirements

None yet.

## Related design documents

- [USE-0003 — Structured Screenshot as Input to an AI System](../../use-cases/USE-0003-structured-screenshot-ai-input.md)
- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-10-18 — links to the initial DRAFT research cards added and later redirected to their English mirrors; status remains `OPEN`.

- 2026-10-18 — scope expanded with the effects of ordinary editing on CV-annotation geometry and semantic currency; status remains `OPEN`.
- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with annotation behavior during modification and sanitization from USE-0002; status remains `OPEN`.
