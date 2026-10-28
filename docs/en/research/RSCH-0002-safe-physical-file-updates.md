# RSCH-0002. Safe Physical File Updates

**Status:** DRAFT  
**Area:** Storage / Recovery / Safety  
**Related questions:** Q-0002, Q-0012, Q-0014  
**Related requirements:** none  
**Related use cases:** USE-0002, USE-0004

**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which verified approaches allow a complex file to be updated without retaining removed values in old blocks or indexes and without presenting a partial result as successful?

## 2. Scope

Includes copy-on-write, complete and partial rebuilding, journaling and atomic schemes, backup indexes, free areas, unknown-block handling, failures, and recovery. The research compares existing approaches but does not assign a particular IMXO write scheme.

### Completion Criteria

At least three update classes are compared; failure and residual-data models are described; properties verifiable independently of the selected container are identified.

## 3. Sources

- specifications of containers and file models that support updating and recovery;
- implementation and format documentation covering free areas, indexes, and crash recovery;
- publications and test methods for residual data and atomic file replacement.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate sanitization guarantee boundaries, error reporting, failure fixtures, and the relationship between the physical model and Q-0014.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

Also examine the physical consequences of ordinary moving, copying, splitting, merging, cropping, and overlapping of objects and fragments, including safe completion of a partially supported operation. Ordinary editing must be distinguished from sanitization and its requirement to remove selected data.

## 7. Open Questions

It is unknown when a local update is sufficient, how preservation of unknown blocks can safely coexist with removal, and which guarantees are available on different file systems.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0002](../project/questions/Q-0002-physical-file-structure.md), [Q-0012](../project/questions/Q-0012-conformance-model.md), [Q-0014](../project/questions/Q-0014-safe-editing-cascade-operations.md)
- Use cases: [USE-0002](../use-cases/USE-0002-safe-sanitization.md), [USE-0004](../use-cases/USE-0004-structured-image-editing.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-28 — linked published USE-0004; status remains `DRAFT`.

- 2026-10-18 — research definition expanded with ordinary fragment-editing cases in preparation for planned USE-0004; status remains `DRAFT`.
- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
