# Q-0010. Accessibility Model

**Status:** OPEN  
**Area:** Accessibility  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the normative IMXO accessibility model be?

## Context

IMXO provides for accessibility data, but its exact normative representation has not yet been defined.

Accessibility in IMXO must be treated as more than a generic metadata field. Research should distinguish intrinsic information that can be stored with the image from contextual alternatives that depend on how the image is used; file-level semantics from application or viewer behavior; and exposure through platform accessibility APIs from regulatory or procurement mappings.

The presence of programmatically available text or an embedded description must not by itself be treated as evidence of legal or WCAG compliance.

## Scope

- alt-like description;
- whole-image description;
- descriptions of individual regions;
- programmatically available text associated with visual regions;
- language information and attributes;
- intrinsic descriptions versus contextual alternative text;
- reading order and relationships among elements;
- semantics for decorative or non-informative content, if supported by research evidence;
- accessible exposure by viewers and SDKs;
- discrepancies between visible pixels and accessibility layers;
- provenance and trust for accessibility data;
- relationships with text and semantic layers;
- interaction with the text model and text fallback strategy;
- whether an accessibility profile would be useful.

## Related questions

- [Q-0013 — Accessibility Standards, Regulatory Mapping, and Adoption](Q-0013-accessibility-regulatory-adoption.md)

## Related research

Not assigned yet.

## Related requirements

None yet.

## Related design documents

None yet.

## Resolution

Not resolved.

## History

- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-09-20 — scope expanded to cover external data exposure, trust, contextual alternatives, and the relationship with Q-0013; status remains `OPEN`.
