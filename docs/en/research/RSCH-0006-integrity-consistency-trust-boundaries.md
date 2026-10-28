# RSCH-0006. Integrity, Consistency, and Trust Boundaries

**Status:** DRAFT  
**Area:** Integrity / Trust  
**Related questions:** Q-0007, Q-0008, Q-0012  
**Related requirements:** none  
**Related use cases:** USE-0002, USE-0003, USE-0004

**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

How do existing systems distinguish file integrity, capture fidelity, internal consistency among representations, currency of an external source, and trust in an assertion?

## 2. Scope

Includes accidental-damage detection, hashes and signatures, raster/structure consistency, trust indicators, unknown state, and verification scope. Excludes selection of cryptographic architecture and any promise that content is true.

### Completion Criteria

Each property is defined separately; what it proves and does not prove is shown; the comparison is applied to USE-0002/0003 without requiring cryptography.

## 3. Sources

- normative integrity, signature, and media-provenance specifications;
- standards and official validation models for compound documents;
- usable-security research on presentation of uncertain trust states.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate separate properties and verifiable states for Q-0008/Q-0012, including recalculation of derived data after changes.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

## 7. Open Questions

Verification granularity, sufficient unknown states, the relationship between a signature and semantic consistency, and interface risks of false trust are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0007](../project/questions/Q-0007-provenance-model.md), [Q-0008](../project/questions/Q-0008-integrity-trust-model.md), [Q-0012](../project/questions/Q-0012-conformance-model.md)
- Use cases: [USE-0002](../use-cases/USE-0002-safe-sanitization.md), [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md), [USE-0004](../use-cases/USE-0004-structured-image-editing.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-28 — linked published USE-0004; status remains `DRAFT`.

- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
