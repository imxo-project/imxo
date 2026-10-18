# RSCH-0007. Structured File Sanitization

**Status:** DRAFT  
**Area:** Privacy / Sanitization  
**Related questions:** Q-0002, Q-0012, Q-0014  
**Related requirements:** none  
**Related use cases:** USE-0002  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which verified models and tools remove selected values from visible, hidden, derived, and historical representations in a structured file, and how do they verify the result?

## 2. Scope

Includes PDF/Office and other complex documents, structured-data anonymization, history, derived values, export, and verification. Physical-media erasure is treated only as a boundary. Steganography inside media data is separated into RSCH-0008.

### Completion Criteria

At least three structured-data classes are compared; detection, transformation, and verification are separated; testable implications are stated without requiring a particular implementation.

## 3. Sources

- official format and redaction/sanitization tool documentation;
- normative media-sanitization guidance used to distinguish responsibilities;
- documentation for anonymization/masking and transformation-verification tools;
- published analyses of known sanitization failures.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate common operation properties, failure reporting, and conformance fixtures for Q-0014 without assigning an algorithm or API.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

Also draw the boundary between ordinary editing and sanitization through moving, copying, partial cutting, merging, cropping, and overlapping examples. Determine which states and residual data may be acceptable in ordinary editing but are unacceptable in a result claimed to be sanitized.

## 7. Open Questions

The sufficient cascade scope, verifiability of absence of derived values, and transfer of guarantees during export are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0002](../project/questions/Q-0002-physical-file-structure.md), [Q-0012](../project/questions/Q-0012-conformance-model.md), [Q-0014](../project/questions/Q-0014-safe-editing-cascade-operations.md)
- Use cases: [USE-0002](../use-cases/USE-0002-safe-sanitization.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition expanded with ordinary fragment-editing cases in preparation for planned USE-0004; status remains `DRAFT`.
- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
