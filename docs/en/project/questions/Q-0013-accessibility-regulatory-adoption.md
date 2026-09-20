# Q-0013. Accessibility Standards, Regulatory Mapping, and Adoption

**Status:** OPEN  
**Area:** Accessibility / Adoption / Standards mapping  
**Source:** PREP-07 discussion  
**Created:** 2026-09-20

## Question

How should IMXO map its accessibility capabilities to external accessibility standards and regulatory frameworks, and to what extent can accessibility requirements become a practical adoption driver for a structured image format?

## Context

IMXO does not currently assume that better compression will be its primary advantage over established image codecs.

Structured accessibility capabilities may provide a different adoption path if IMXO can preserve information that is otherwise lost when content is flattened into pixels, including programmatically available text, language information, semantic regions, accessible descriptions, and relationships between visual and textual content.

Relevant external frameworks include, at minimum:

- European Accessibility Act / Directive (EU) 2019/882;
- WCAG, including criteria related to non-text content and images of text;
- EN 301 549;
- U.S. Section 508;
- ADA-related accessibility requirements and implementation practice;
- other relevant national or sector-specific accessibility frameworks discovered during research.

None of these frameworks should be assumed to require IMXO.

The research must distinguish between:

- legal requirements;
- technical accessibility standards;
- procurement requirements;
- implementation guidance;
- capabilities of the IMXO file format itself;
- behavior required from viewers, SDKs, applications, operating systems, or assistive technologies;
- adoption and procurement arguments.

## Research questions

1. Which accessibility requirements materially affect images, screenshots, images of text, embedded text, and structured visual content?
2. Which requirements can be supported directly by file-level semantics?
3. Which requirements necessarily depend on viewer/application behavior?
4. What role can programmatically available text play compared with flattened images of text?
5. What kinds of intrinsic descriptions can be stored in a file, and which accessibility alternatives remain context-dependent?
6. Should IMXO distinguish intrinsic description from contextual alternative text?
7. Are language tags, reading order, semantic regions, decorative-content indicators, or similar metadata needed?
8. What accessibility data must be exposed through platform accessibility APIs to be useful in practice?
9. Could a future IMXO Accessibility Profile be useful, and what should it mean?
10. How should IMXO publish versioned mappings to WCAG / EN 301 549 / Section 508 / other frameworks without hard-coding the core format to a particular regulatory version?
11. Which public claims about accessibility can be supported, and which would overstate compliance?
12. Can accessibility requirements create a meaningful adoption or procurement driver for IMXO even if IMXO does not outperform modern codecs in compression?
13. Which jurisdictions or procurement regimes provide the strongest practical adoption incentives?
14. What accessibility requirements should become project-level `REQ` items after research?

## Boundaries

This question does not decide:

- that IMXO is legally required anywhere;
- that storing text automatically satisfies WCAG;
- that a built-in description automatically satisfies alternative-text requirements;
- that any particular accessibility profile should exist;
- the exact fields or binary representation of accessibility data;
- the final conformance model.

Those decisions require research and the normal `RSCH / REQ / DES / ADR / SPEC` process.

## Related questions

- Q-0010 — Accessibility model
- Q-0003 — Logical object model
- Q-0006 — Text, fonts and glyph fallback
- Q-0012 — Conformance model

## Initial authoritative sources to examine

- Directive (EU) 2019/882 — European Accessibility Act
- WCAG 2.2
- EN 301 549 and the legally referenced / current published editions relevant at the time of research
- U.S. Revised Section 508 Standards
- U.S. ADA web/mobile accessibility rules and official guidance

Exact versions, legal status, dates, and applicability must be verified in RSCH before being relied upon.

## Current result

No architectural decision has been made.

The question remains OPEN.

## History

- 2026-09-20 — Created after PREP-07 discussion to separate regulatory/adoption research from the technical accessibility-model question.

