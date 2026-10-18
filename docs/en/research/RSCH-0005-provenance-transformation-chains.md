# RSCH-0005. Provenance and Transformation Chains

**Status:** DRAFT  
**Area:** Provenance  
**Related questions:** Q-0007, Q-0009  
**Related requirements:** none  
**Related use cases:** USE-0001, USE-0002, USE-0003  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which existing provenance models distinguish the source of an assertion, transformations, human and machine verification, and reuse without losing origin information?

## 2. Scope

Includes creation and transformation chains, agents and tools, independent and derived assertions, transfer between systems, provenance sensitivity, and removal without retaining the former value. Excludes mandatory signatures and a specific IMXO model.

### Completion Criteria

Models are compared on chains with several transformations; independence of evidence, sanitization, and data minimization are examined separately.

## 3. Sources

- W3C PROV and other normative provenance models;
- specifications for digital-media provenance chains;
- primary documents on dataset/model lineage and assertion transformations.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate required granularity, inheritance, and provenance trust boundaries for Q-0007 and reuse of machine assertions.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

Also study the provenance of derived fragments after copying, moving, splitting, and merging, distinguishing a transformation chain from complete image history. A common source must not be treated as automatic confirmation of the current classification of every fragment; privacy and sanitization constraints remain in force.

## 7. Open Questions

The minimum chain, provenance-compaction rules, representation of external sources, and safe removal of sensitive origin details are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0007](../project/questions/Q-0007-provenance-model.md), [Q-0009](../project/questions/Q-0009-cv-annotations.md)
- Use cases: [USE-0001](../use-cases/USE-0001-structured-screenshot-content.md), [USE-0002](../use-cases/USE-0002-safe-sanitization.md), [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition expanded with ordinary fragment-editing cases in preparation for planned USE-0004; status remains `DRAFT`.
- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
