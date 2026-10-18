# RSCH-0001. Container Architecture Comparison

**Status:** DRAFT  
**Area:** Container / Physical model  
**Related questions:** Q-0001, Q-0002  
**Related requirements:** none  
**Related use cases:** USE-0001, USE-0002, USE-0003  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which existing container architectures, and which custom-format alternative, provide the best-founded starting capabilities and constraints for the IMXO physical model?

## 2. Scope

Includes JUMBF/JLINK, ISO BMFF/HEIF, RIFF, PNG chunks, TIFF/BigTIFF, ZIP-like models, and well-founded alternatives discovered during research. Compares extensibility, independent reading, streaming, unknown extensions, indexing, recovery, and adoption cost. Excludes architecture selection, IMXO binary design, and an ADR.

### Completion Criteria

A single criteria matrix is prepared; each primary option is checked against primary sources; facts, interpretations, and gaps are explicitly separated; comparable implications are stated without selecting a winner.

## 3. Sources

- normative specifications and official registries for the formats under review;
- official compatibility and extension material;
- available reference implementations and conformance material as supporting sources.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate implications for Q-0001/Q-0002 and later requirements for extensibility, safe reading, and verifiability without selecting a container.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

## 7. Open Questions

Comparable overhead, constraints on unknown extensions, and the adequacy of ready-made containers for the linked IMXO object model are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0001](../project/questions/Q-0001-container-architecture.md), [Q-0002](../project/questions/Q-0002-physical-file-structure.md)
- Use cases: [USE-0001](../use-cases/USE-0001-structured-screenshot-content.md), [USE-0002](../use-cases/USE-0002-safe-sanitization.md), [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
