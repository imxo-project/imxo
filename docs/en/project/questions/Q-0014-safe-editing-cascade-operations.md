# Q-0014. Safe Modification, Dependencies, and Cascade Operations

**Status:** OPEN  
**Area:** Editing / Safety  
**Source:** USE-0002  
**Created:** 2026-10-01

## Question

How should IMXO define the semantics of safe modification and removal operations over related structured content so that a correct implementation can process the complete reliably known dependency chain and determine whether the operation completed successfully?

## Context

`USE-0002` established the expected scenario behavior: removed content must not remain inside the particular final file in related or derived representations merely because they occupy another part of the structure.

The specific mechanism must not be selected inside an informative `USE`. This question connects operation semantics to the logical model in `Q-0003`, the physical model in `Q-0002`, SDKs in `Q-0011`, and the conformance model in `Q-0012`.

Two operation classes are distinguished here. **Ordinary editing** changes visible and/or structured content without necessarily guaranteeing irreversible removal of the original content. **Sanitization** removes selected data and processes reliably known dependent and derived representations in accordance with `USE-0002`.

## Scope

- the distinction among concealment (`hide`), replacement (`replace`), removal (`delete`), sanitization (`sanitize`), and cropping (`crop`);
- moving and copying an entire object or part of one;
- splitting and merging fragments, cropping, and overlapping;
- recalculating geometry separately from reviewing semantic annotations and relationships;
- partially supported operations, unknown dependencies, and behavior when consistency cannot be preserved;
- the boundary of one logical operation;
- traversal of known dependencies and cascading removal;
- partially affected and fully contained dependent objects;
- distinguishing dependency from simple geometric intersection;
- derived representations, hashes, and other derived values;
- several alternative annotations and marking an annotation stale;
- previous states within the same file;
- opaque embedded data and extensions;
- behavior when a dependency cannot be processed safely;
- operation integrity under failure and verification of the result after modification;
- the boundary among format, library, and application responsibilities.

Q-0014 does not determine a universal cascade algorithm, mandatory transformation history, mandatory retention of former pixels, a specific reference format, dependency-graph structure, mandatory full file rebuild, particular library API, mandatory use of AI, particular transactional-write model, or built-in cryptography.

Planned `USE-0004` will separately examine ordinary editing of a structured image; this question card neither replaces that scenario nor decides it in advance.

## Related questions

- [Q-0002 — Physical File Structure](Q-0002-physical-file-structure.md)
- [Q-0003 — Logical Object Model](Q-0003-logical-object-model.md)
- [Q-0007 — Provenance Model](Q-0007-provenance-model.md)
- [Q-0008 — Integrity / Trust Model](Q-0008-integrity-trust-model.md)
- [Q-0009 — Computer Vision Annotations](Q-0009-cv-annotations.md)
- [Q-0011 — SDKs and Integrations](Q-0011-sdk-integrations.md)
- [Q-0012 — Conformance Model](Q-0012-conformance-model.md)

## Related research

- [RSCH-0002 — Safe Physical File Updates](../../research/RSCH-0002-safe-physical-file-updates.md)
- [RSCH-0004 — Object Relationships and Alternative Assertions](../../research/RSCH-0004-object-relationships-alternative-assertions.md)
- [RSCH-0007 — Structured File Sanitization](../../research/RSCH-0007-structured-file-sanitization.md)
- [RSCH-0008 — Media Steganography and Steganalysis](../../research/RSCH-0008-media-steganography-steganalysis.md)

## Related requirements

None yet.

## Related design documents

- [USE-0003 — Structured Screenshot as Input to an AI System](../../use-cases/USE-0003-structured-screenshot-ai-input.md)
- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)
- [USE-0001 — Screenshot Preserving Structured User Content](../../use-cases/USE-0001-structured-screenshot-content.md)

## Resolution

Not resolved.

## History

- 2026-10-18 — links to the initial DRAFT research cards added and later redirected to their English mirrors; status remains `OPEN`.

- 2026-10-18 — distinction between ordinary editing and sanitization clarified; operations over whole objects and fragments added; status remains `OPEN`.
- 2026-10-01 — question created from the development of USE-0002; status `OPEN`, no resolution accepted.
