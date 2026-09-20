# IMXO Open Questions

This document is a living index of material project questions that have not yet received a final resolution.

The initial `Q-0001…Q-0012` questions were transferred from `PREP-00`. PREP-00 remains a historical checkpoint, while the current state of the questions is tracked here and in their individual cards. Question `Q-0013` was added following PREP-07.

## Rules

- allowed statuses are `OPEN`, `RESOLVED`, and `SUPERSEDED`;
- `Q-xxxx` identifiers are never reused;
- a question is not removed after it is closed;
- each material question has its own Markdown card;
- after PREP-05, a new material question begins with a GitHub Issue and receives a `Q-xxxx` identifier when appropriate after initial review.

## Registry

| ID | Question | Status | Area |
|---|---|---|---|
| [Q-0001](questions/Q-0001-container-architecture.md) | IMXO container architecture | `OPEN` | Container |
| [Q-0002](questions/Q-0002-physical-file-structure.md) | Physical file structure | `OPEN` | Container |
| [Q-0003](questions/Q-0003-logical-object-model.md) | Logical object model | `OPEN` | Logical model |
| [Q-0004](questions/Q-0004-identification.md) | MIME type, magic, and brand | `OPEN` | Identification |
| [Q-0005](questions/Q-0005-versioning.md) | IMXO versioning | `OPEN` | Versioning |
| [Q-0006](questions/Q-0006-text-fonts-glyph-fallback.md) | Text, fonts, and glyph fallback | `OPEN` | Text |
| [Q-0007](questions/Q-0007-provenance-model.md) | Provenance model | `OPEN` | Provenance |
| [Q-0008](questions/Q-0008-integrity-trust-model.md) | Integrity / Trust model | `OPEN` | Security / Trust |
| [Q-0009](questions/Q-0009-cv-annotations.md) | Computer Vision annotations | `OPEN` | Annotations / CV |
| [Q-0010](questions/Q-0010-accessibility-model.md) | Accessibility model | `OPEN` | Accessibility |
| [Q-0011](questions/Q-0011-sdk-integrations.md) | SDKs and integrations | `OPEN` | Implementation |
| [Q-0012](questions/Q-0012-conformance-model.md) | Conformance model | `OPEN` | Conformance |
| [Q-0013](questions/Q-0013-accessibility-regulatory-adoption.md) | Accessibility standards, regulatory mapping, and adoption | `OPEN` | Accessibility / Adoption / Standards mapping |

## Adding new questions

The next available identifier is `Q-0014`.

A new material question is first submitted through a GitHub Issue. After the maintainer decides to include it in the formal process, a card is created from `Q-template.md`, the next permanent `Q-xxxx` identifier is assigned, and this index is updated.
