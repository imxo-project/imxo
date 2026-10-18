# RSCH-0009. Partial Representations and Selective Extraction

**Status:** DRAFT  
**Area:** Logical model / Processing  
**Related questions:** Q-0003, Q-0011, Q-0012  
**Related requirements:** none  
**Related use cases:** USE-0003  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

How can completeness of a selectively extracted representation be described correctly relative to request scope, known types, relationships, provenance, and reader capabilities?

## 2. Scope

Includes partial responses, projection, filtering, pagination, unknown extensions, unsupported types, and the distinction between absence and uncertainty. Covers semantics and verifiability, not a specific API or the physical cost of reading.

### Completion Criteria

Verifiable terminology for absent/unknown/unsupported/not requested is established; models are applied to several selection types; necessary negative tests are identified.

## 3. Sources

- normative partial-response and structured-data projection models;
- specifications of extensible formats with unknown or unsupported content;
- official API documents that explicitly define response completeness and capability negotiation.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate completeness states and safe-use rules for partial results for Q-0003/Q-0011/Q-0012 and USE-0003 adapters.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

Also examine an editor that supports only part of the structure: how changed geometry, unsupported relationships, and unknown assertion currency are conveyed after fragments are moved, copied, split, or merged without presenting a partially processed state as complete.

## 7. Open Questions

Minimum completeness scopes, handling of omitted relationships, and means to avoid conflating semantic selection with a promise of inexpensive physical reading are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0003](../project/questions/Q-0003-logical-object-model.md), [Q-0011](../project/questions/Q-0011-sdk-integrations.md), [Q-0012](../project/questions/Q-0012-conformance-model.md)
- Use cases: [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition expanded with ordinary fragment-editing cases in preparation for planned USE-0004; status remains `DRAFT`.
- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
