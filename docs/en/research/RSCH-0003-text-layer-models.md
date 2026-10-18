# RSCH-0003. Text Layer Models

**Status:** DRAFT  
**Area:** Text / Representation  
**Related questions:** Q-0003, Q-0006  
**Related requirements:** none  
**Related use cases:** USE-0001  
**Supersedes:** none  
**Created:** 2026-10-18

## 1. Research Question

Which existing models best describe text, its geometry, language properties, fonts, and glyph fallback in a structured image?

## 2. Scope

Includes text layers in document and image formats, OCR output as a derived assertion, Unicode, language tags, writing direction, logical order, geometry, and reproduction strategies. Excludes a built-in OCR engine and a final IMXO field model.

### Completion Criteria

Models are compared against a common set of multilingual and geometric scenarios; OCR provenance, fallback, and unresolved implementation questions are described separately.

## 3. Sources

- normative Unicode, BCP 47, and relevant text-model specifications;
- official ALTO and PDF/SVG text-layer specifications or other verified formats;
- primary documentation for fonts, glyph fallback, and complex text layout.

For every source used, record the organization or author, exact edition or version, date, link, and relevant sections. Check currency, primacy, and applicability; marketing claims are not evidence.

## 4. Established Facts

Not researched yet.

## 5. Analysis

Research required.

## 6. Implications for IMXO

Evaluate the distinctions required among content, representation, recognized text, and visual reproduction for Q-0003/Q-0006.

Until the research is complete, this section lists only matters to evaluate and is not a requirement, design decision, or recommendation.

## 7. Open Questions

The minimum portable text-geometry model, the boundary for storing fonts, and representation of multiple textual assertions are unknown.

## 8. Conclusion

Not researched yet. Conclusions and possible recommendations will appear only after source verification and analysis; they will not become an architectural decision without a separate ADR process.

## 9. Related Documents

- Questions: [Q-0003](../project/questions/Q-0003-logical-object-model.md), [Q-0006](../project/questions/Q-0006-text-fonts-glyph-fallback.md)
- Use cases: [USE-0001](../use-cases/USE-0001-structured-screenshot-content.md)

- Requirements: none
- Design: none
- ADR: none

## 10. History

- 2026-10-18 — research definition created; status DRAFT, substantive research not started.
- 2026-10-18 — complete English mirror created without changing the research status or findings.
