# RSCH-0008. Media Steganography and Limits of Steganalysis

**Status:** DRAFT  
**Area:** Security / Media  
**Related questions:** Q-0008, Q-0014  
**Related requirements:** none  
**Related use cases:** USE-0002  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which hidden-channel classes exist in raster and other media content, what can practical steganalysis and normalization methods detect or disrupt, and where do their guarantees end?

## 2. Scope

Includes known embedding classes, payload survival through transformations, detection limits, false positives, and specialized inspection modes. Excludes ordinary IMXO structural dependencies, design of a built-in steganalyzer, and any promise of universal detection.

### Completion Criteria

Major channel and transformation classes are covered; limitations and uncertainty are supported by sources and an experimental method; structural sanitization remains a separate task.

## 3. Sources

- NIST and other authoritative definitions and guidance;
- peer-reviewed research on steganalysis methods and limitations;
- official documentation for open tools and reproducible test sets.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Clarify the USE-0002 guarantee boundary and Q-0008/Q-0014 terminology without making steganalysis a mandatory IMXO feature.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

## 7. Open Questions

Realistic guarantees for different codecs, channel resilience under transformations, and acceptable additional inspection cost are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0008](../project/questions/Q-0008-integrity-trust-model.md), [Q-0014](../project/questions/Q-0014-safe-editing-cascade-operations.md)
- Use cases: [USE-0002](../use-cases/USE-0002-safe-sanitization.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
