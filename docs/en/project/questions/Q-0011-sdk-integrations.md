# Q-0011. SDKs and Integrations

**Status:** OPEN  
**Area:** Implementation  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the future IMXO SDK, API, and integration model be after the core architecture stabilizes?

## Context

PREP-00 makes no final decisions about SDKs and integrations. These questions will be considered later, once the core models are sufficiently stable. Planned USE-0004 requires consideration of editors with complete and partial structural support without designing an API in advance.

## Scope

- SDKs and APIs;
- Windows, Linux, macOS, and Android;
- browsers;
- Photoshop, GIMP, and Krita;
- system image viewers;
- viewer/editor integration;
- capture tools;
- high-level safe modification and removal operations without prematurely assigning specific APIs;
- high-level ordinary-editing operations for moving, copying, splitting, merging, cropping, and overlapping without defining specific SDK calls;
- reporting that related assertions have not had their currency revalidated after a change;
- partial editor support for structure without silently declaring the result fully consistent;
- safe propagation of state and known limitations after changes;
- handling related changes and removals and verifying the final state;
- enabling correct implementation without requiring every application to traverse internal container structures manually;
- behavior with partially supported extensions and production of a state suitable for export.

## Related research

- [RSCH-0009 — Partial Representations and Selective Extraction](../../research/RSCH-0009-partial-representations-selective-extraction.md)
- [RSCH-0011 — AI Input Preparation Efficiency Comparison](../../research/RSCH-0011-ai-input-efficiency-comparison.md)

## Related requirements

None yet.

## Related design documents

- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-10-18 — links to the initial DRAFT research cards added and later redirected to their English mirrors; status remains `OPEN`.

- 2026-10-18 — scope expanded with high-level ordinary-editing operations and state propagation after changes; status remains `OPEN`.
- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with library operations for safe modification from USE-0002; status remains `OPEN`.
