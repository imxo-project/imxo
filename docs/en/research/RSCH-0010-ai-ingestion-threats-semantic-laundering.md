# RSCH-0010. AI Ingestion Threats and Semantic Laundering

**Status:** DRAFT  
**Area:** Security / AI consumption  
**Related questions:** Q-0007, Q-0008, Q-0012  
**Related requirements:** none  
**Related use cases:** USE-0003  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which threats arise when raster and structured assertions are supplied to an AI system, including instruction injection, loss of context, and re-presentation of a derived output as an independent fact?

## 2. Scope

Includes prompt injection through visible and structured data, the data/instructions boundary, adapters, provenance loss, semantic laundering, and authority of the execution system. Excludes an autonomous-action protocol, IMXO prompts, and embedded active logic.

### Completion Criteria

A threat model identifies assets, trust boundaries, and abuses; mitigations are separated among the format, adapter, model, and execution system; active behavior is not moved into IMXO.

## 3. Sources

- OWASP and other authoritative threat-model documents for LLM and agent systems;
- primary platform documentation on separation of data, tools, and instructions;
- peer-reviewed research on indirect prompt injection and provenance loss.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate threats and test scenarios for Q-0007/Q-0008/Q-0012 while keeping IMXO static and passive.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

## 7. Open Questions

Sufficient adapter boundaries, propagation of untrusted-data markings, and means to detect cyclical amplification of derived assertions are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0007](../project/questions/Q-0007-provenance-model.md), [Q-0008](../project/questions/Q-0008-integrity-trust-model.md), [Q-0012](../project/questions/Q-0012-conformance-model.md)
- Use cases: [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
