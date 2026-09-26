# IMXO Use Cases

This directory contains informative `USE` cards describing IMXO application scenarios.

A `USE` answers:

> who or which system, in what context, addresses which problem, and what outcome is needed?

A `USE` is not:

- a normative requirement;
- an architectural decision;
- research evidence;
- a promise to include a feature in a particular standard version.

`Status` describes document maturity, while `Disposition` describes the scenario's place in the project; these characteristics are independent. The `USE` process and lifecycle are defined in [`PREP-08`](../project/PREP-08-use-case-research-planning-process-amendment.md). New cards use the [`USE-template.md`](../templates/USE-template.md) template.

## Status values

A card may have one of these statuses:

- `DRAFT`
- `REVIEW`
- `COMPLETE`
- `WITHDRAWN`
- `SUPERSEDED`

## Disposition values

Independently of document maturity, a card has one of these dispositions:

- `CANDIDATE`
- `TARGET`
- `NON-TARGET`
- `DEFERRED`

`COMPLETE` means that the scenario description is mature.

`TARGET` means that the scenario is treated as a target for IMXO development.

Neither state automatically creates normative requirements.

## Cards

| ID | Name | Status | Disposition | Summary |
|---|---|---|---|---|
| [`USE-0001`](USE-0001-structured-screenshot-content.md) | [Screenshot Preserving Structured User Content](USE-0001-structured-screenshot-content.md) | `REVIEW` | `CANDIDATE` | Preserves the visual screenshot together with safe, spatially associated text and user-relevant semantics without turning the file into a dump of application state. |

## Planned use cases

The entries below are only a working roadmap. These cards have not yet been created, have no official PREP-08 `Status` or `Disposition`, and become real `USE` artifacts only when their files are created. The working numbers reflect the currently agreed discussion order.

| Working number | Working title | Why it is needed |
|---|---|---|
| `USE-0002` | Safe concealment and removal of data in a structured image | Explore cascading removal or update of text, semantics, annotations, metadata, and alternative representations across the IMXO editing ecosystem, including future reusable mechanisms in official libraries without prohibiting independent implementations. |
| `USE-0003` | Screenshot as input for an AI agent | Consider automated consumption of a structured screenshot, where representation divergence may influence actions and provenance, trust, and data conflicts become central. |
| `USE-0004` | Image with computer-vision annotations | Describe human- or machine-created boxes, polygons, masks, labels, and other CV annotations, their provenance, relationships to common ecosystems, and continued validity after image editing. |
| `USE-0005` | Long-lived scientific, museum, or archival image | Consider long retention, preservation, migration, offline or self-contained use, provenance, and verification horizons without unnecessary dependence on external services. |
| `USE-0006` | Image with machine-generated semantic annotations | Consider a raster with objects, regions, and descriptions from a camera, capture tool, or later analyzer, the provenance and trust of machine assertions, and reuse of the same information by different consumers. |
| `USE-0007` | Accessible structured image for an assistive-technology user | Consider access beyond alt text to meaningful visual and semantic content for users who cannot fully perceive the raster: text, descriptions, regions, relationships, and existing CV or camera annotations, accounting for their provenance and the distinction between format capabilities and viewer or platform accessibility APIs. |

## Language workflow

New cards are developed in Russian first.

An English version is optional before `COMPLETE`, but may be created earlier for external review or collaboration.

When a card reaches `COMPLETE`, a mirrored English version becomes mandatory.

When both versions exist, they retain the same ID, meaning, Status, Disposition, and relationships with other artifacts.
