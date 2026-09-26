# IMXO

<p align="center">
  <img src="assets/brand/readme/imxo-readme-hero-light.png" alt="IMXO — Image Model eXchange Object">
</p>

<p align="center">
  <a href="#status"><img src="https://img.shields.io/badge/status-research%20%26%20early%20design-7C3AED" alt="Project status: research and early design"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg" alt="Apache License 2.0"></a>
  <a href="LICENSE-CC-BY-4.0.txt"><img src="https://img.shields.io/badge/documentation-CC%20BY%204.0-EF9421?logo=creativecommons&amp;logoColor=white" alt="Documentation: CC BY 4.0"></a>
</p>

<p align="center"><a href="README.ru.md">Русская версия</a></p>

<p align="center"><strong>IMXO — Image Model eXchange Object</strong></p>

IMXO is an open structured image format and standard intended to combine visual content with structured, machine-readable information in a single extensible object.

The project explores a model in which an image is not limited to a flat raster. An IMXO file may contain raster and vector representations, text, semantic regions, annotations, provenance information, integrity data, accessibility information, and multiple related representations of the same visual object.

> IMXO is currently in the research and early design stage. The file format, container layout, logical object model, and conformance rules are not yet finalized.

## Goals

IMXO is being designed to provide a common open representation for images that can be useful to people, applications, AI systems, computer vision tools, editors, viewers, capture tools, and archival workflows.

The project is intended to support, among other things:

- raster image representations;
- vector representations and overlays;
- text associated with image regions;
- semantic regions and relationships;
- multiple annotation sets;
- computer vision annotations;
- provenance and source information;
- integrity and trust-related metadata;
- accessibility descriptions;
- multiple representations of the same image or object;
- safe extensibility and preservation of unknown extensions.

IMXO is not intended to replace every existing raster or vector codec. Existing codecs may be used as representations inside the broader IMXO model.

## Static and passive by design

The first version of the standard follows a strict principle:

**IMXO v0.1 must not contain executable or dynamic behavior.**

The format is intended to remain static and passive. It must not embed JavaScript, macros, event handlers, automatic network requests, executable workflows, externally updated dynamic fields, or similar active behavior.

## Research-first approach

The project does not assume that a completely new container must be invented.

Before the physical and detailed logical model is finalized, the project will study existing container and image-related architectures, including:

- JUMBF / JLINK;
- ISO BMFF / HEIF;
- RIFF;
- PNG chunk architecture;
- TIFF / BigTIFF;
- ZIP-like container models;
- other relevant standards and container systems discovered during research.

The decision between a custom IMXO container, a profile built on an existing container, or a hybrid approach will be made only after this research.

## Current project state

The initial **PREP-00 through PREP-07** preparation baseline was completed. **PREP-08** was added as a targeted process amendment before systematic research began. IMXO remains in the research and early-design stage.

Completed:

- project identity: **IMXO — Image Model eXchange Object**, file extension **`.imxo`**;
- GitHub organization and primary repository;
- project domain: **imxo.org**;
- base repository and documentation structure;
- mixed licensing model and license texts;
- Brand Policy;
- contribution and security infrastructure;
- initial preparation baseline **PREP-00 through PREP-07**;
- targeted **PREP-08** process amendment introducing the informative `USE` artifact class and research-planning rules;
- first real use-case card, `USE-0001`, in synchronized Russian and English versions;
- published project [`GOVERNANCE.md`](GOVERNANCE.md) and [`IPR_POLICY.md`](IPR_POLICY.md).

Next:

The next steps are to expand the initial use-case set, prepare the initial systematic research plan, and only then begin technical work through the project's `RSCH` process.

The container architecture, logical object model, and normative specification remain open and have not been finalized by completion of the PREP cycle.

## Repository structure

The base repository structure has been established. Additional directories and sections will be added as the corresponding research, requirements, design decisions, specification, examples, schemas, and implementation materials emerge.

Documentation indexes: [English](docs/en/README.md) and [Russian](docs/ru/README.md).

Informative `USE` cards describe application scenarios without creating requirements or architecture. They are developed in Russian first; an English mirror becomes mandatory when a card reaches `COMPLETE`. See the [English use-case index](docs/en/use-cases/README.md) or the [Russian use-case index](docs/ru/use-cases/README.md).

Reference implementations, SDKs, tools, and test suites may later remain in this repository or move into separate repositories under the IMXO organization depending on their lifecycle and scope.

## Languages

Project documentation is maintained in **English and Russian** using mirrored structures.

At the next stage, new substantive research and design documents are prepared in Russian first. An English version is created after the structure has been discussed and the Russian text approved. Existing public English and Russian documents remain aligned with the factual project state.

When the project reaches a stable normative specification, the English version is expected to become the normative language, with the Russian version maintained as an official synchronized translation.

Technical identifiers, field names, object names, requirement identifiers, and document identifiers are not translated.

## Licensing

The repository uses a mixed licensing model:

- Source code and machine-readable implementation materials use the **Apache License 2.0**. See [`LICENSE`](LICENSE).
- Specification text, research, design documentation, and general documentation use **Creative Commons Attribution 4.0 International (CC BY 4.0)**. See [`LICENSE-CC-BY-4.0.txt`](LICENSE-CC-BY-4.0.txt).
- Official IMXO logos, Kumixo artwork, and other brand assets are excluded from the general code and documentation licenses and are governed by [`BRAND_POLICY.md`](BRAND_POLICY.md).

See [`LICENSES.md`](LICENSES.md) for the scope of each license.

## Governance

IMXO currently uses a founder-led, maintainer-based governance model with open participation and publicly traceable technical decisions.

The current governance model is described in [`GOVERNANCE.md`](GOVERNANCE.md).

Patent and similar implementation-related intellectual-property matters are addressed separately in [`IPR_POLICY.md`](IPR_POLICY.md).

## Project identity

- **Name:** IMXO
- **Expansion:** Image Model eXchange Object
- **File extension:** `.imxo`
- **Website:** https://imxo.org
- **GitHub organization:** https://github.com/imxo-project

## Status

IMXO is experimental and under active design.

No current document should be treated as a final standard unless it is explicitly marked as normative and released as part of a future stable specification.

## Citation

Citation metadata is provided in [`CITATION.cff`](CITATION.cff). It intentionally omits a release version and date while IMXO remains in the research and early design stage.

---

Contributions, technical criticism, alternative designs, and implementation feedback are welcome. See [`CONTRIBUTING.md`](CONTRIBUTING.md) before submitting an Issue or pull request.
