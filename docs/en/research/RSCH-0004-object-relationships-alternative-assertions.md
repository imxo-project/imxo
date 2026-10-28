# RSCH-0004. Objects, Relationships, and Alternative Assertions

**Status:** DRAFT  
**Area:** Logical model / Semantics  
**Related questions:** Q-0003, Q-0009, Q-0014  
**Related requirements:** none  
**Related use cases:** USE-0001, USE-0002, USE-0003, USE-0004

**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

How do existing models represent objects, spatial and semantic relationships, dependencies, and several nonmatching assertions about the same visual content?

## 2. Scope

Includes object identity, regions, parent/child and derived-from relationships, alternative annotation sets, conflict, uncertainty, and staleness after modification. Geometric intersection is not automatically treated as dependency. Excludes a specific IMXO graph or schema.

### Completion Criteria

Models are tested against common USE-0001/0002/0003 examples; geometry, semantics, and dependency are distinguished; open alternatives are stated without selecting a schema.

## 3. Sources

- normative annotation, provenance, and structured-document models;
- official schemas from common computer-vision and accessibility ecosystems;
- peer-reviewed models for conflicting and alternative assertions.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate concepts needed by the logical model and safe cascade operations without turning an external schema into an IMXO design decision.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

Also compare representation of a visual region, object identity, and an assertion about it during moving, copying, splitting, and merging. Examine one object represented in several regions, several descriptions of one fragment, and part-whole relationships without deriving semantic classification from transformed geometry alone.

## 7. Open Questions

The minimum relationship types, object-identity boundary, and means of marking incompleteness, conflict, or a stale state are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0003](../project/questions/Q-0003-logical-object-model.md), [Q-0009](../project/questions/Q-0009-cv-annotations.md), [Q-0014](../project/questions/Q-0014-safe-editing-cascade-operations.md)
- Use cases: [USE-0001](../use-cases/USE-0001-structured-screenshot-content.md), [USE-0002](../use-cases/USE-0002-safe-sanitization.md), [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md), [USE-0004](../use-cases/USE-0004-structured-image-editing.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-28 — linked published USE-0004; status remains `DRAFT`.

- 2026-10-18 — research definition expanded with ordinary fragment-editing cases in preparation for planned USE-0004; status remains `DRAFT`.
- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
