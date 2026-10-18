# RSCH-0012. CV Annotation Interchange Formats

**Status:** DRAFT  
**Area:** Annotations / CV  
**Related questions:** Q-0003, Q-0009  
**Related requirements:** none  
**Related use cases:** USE-0001, USE-0003  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which existing CV-annotation formats and ecosystems represent boxes, polygons, masks, points, labels, confidence, provenance, and several assertion sets, and what is lost during conversion?

## 2. Scope

Includes common open dataset and annotation-interchange formats, human and machine sources, geometry, categories, confidence, and mapping losses. Excludes selection of a normative IMXO schema and treats future USE-0005/0007 as unpublished planning topics.

### Completion Criteria

Major annotation types and at least three ecosystems are compared; conversions are tested on examples; losses and incompatible concepts are listed separately.

## 3. Sources

- official specifications or canonical schemas for annotation formats;
- primary documentation for supporting tools;
- open converters and test datasets for checking round-trip losses.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate shared concepts and boundaries for mapping external schemas for Q-0009 and the logical model while keeping alternative sets independent.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

Also compare how common formats behave when an entire object is moved or copied, a mask/bounding box/polygon is partially changed, or fragments are split and joined. Structural recalculation of geometry must be evaluated separately from renewed confirmation of a semantic label.

## 7. Open Questions

The minimum common set, transfer of provenance/confidence, category ambiguity, and achievable degree of round-trip preservation are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0003](../project/questions/Q-0003-logical-object-model.md), [Q-0009](../project/questions/Q-0009-cv-annotations.md)
- Use cases: [USE-0001](../use-cases/USE-0001-structured-screenshot-content.md), [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition expanded with ordinary fragment-editing cases in preparation for planned USE-0004; status remains `DRAFT`.
- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
