# Q-0009. Computer Vision Annotations

**Status:** OPEN  
**Area:** Annotations / CV  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

How should IMXO represent computer vision annotations and map external schemas?

## Context

IMXO must support multiple annotation sets from different sources. The boundary between normative IMXO concepts and mappings from external systems must be defined.

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
- removal or update of related annotations during sanitization.

## Related research

Not assigned yet.

## Related requirements

None yet.

## Related design documents

- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with annotation behavior during modification and sanitization from USE-0002; status remains `OPEN`.
