# RSCH-0011. AI Input Preparation Comparison

**Status:** DRAFT  
**Area:** AI / Evaluation  
**Related questions:** Q-0011, Q-0012  
**Related requirements:** none  
**Related use cases:** USE-0003  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

For which tasks and conditions do raster, raster with OCR, direct UI/API access, PNG with JSON/XML, SVG, PDF, IMXO, and selective structure differ in quality, errors, latency, volume, and total cost?

## 2. Scope

Includes development of a reproducible method and a later experiment on equivalent tasks. Tokens are only one metric. Semantic experiments may precede the container; physical IMXO costs can be measured only with a prototype. Excludes marketing claims of efficiency and optimization for one model.

### Completion Criteria

A reproducible protocol is approved; equivalent tasks are compared with confidence bounds and error analysis; semantic and physical costs are reported separately.

## 3. Sources

- official documentation for the compared interfaces and formats;
- published evaluation methods for multimodal, OCR, and agent inputs;
- reproducible models, datasets, profilers, and measurements with recorded versions.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate whether structured input provides measurable benefit, which data classes are needed, and what verification costs it adds.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

## 7. Open Questions

Benchmark tasks, models, sample sizes, quality metrics, and the point when a sufficient prototype exists for physical measurements have not been defined.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0011](../project/questions/Q-0011-sdk-integrations.md), [Q-0012](../project/questions/Q-0012-conformance-model.md)
- Use cases: [USE-0003](../use-cases/USE-0003-structured-screenshot-ai-input.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
