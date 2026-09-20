# IMXO project context

## Project identity

**Project:** IMXO  
**Normative expansion:** Image Model eXchange Object  
**File extension:** `.imxo`  
**GitHub organization:** https://github.com/imxo-project

IMXO is an open structured image format and standard.

The central idea is that an image is treated not only as a flat raster, but as an extensible object that can contain visual representations and related machine-readable data.

Potential IMXO content includes raster representations, vector representations and overlays, text, regions, annotations, semantic relationships, provenance, integrity and trust information, accessibility data, and multiple related representations.

The project is at an early research and design stage. The file format, container layout, logical object model, and conformance rules are not yet finalized.

## Critical v0.1 baseline

IMXO v0.1 must be **static and passive**.

The accepted baseline excludes:

- JavaScript;
- macros;
- embedded scripts;
- event handlers;
- automatic network requests;
- executable actions;
- externally updated fields;
- dynamic business logic;
- scripted animation;
- any other active behavior inside the file.

Ideas involving active behavior may be researched only when explicitly identified as outside the accepted v0.1 baseline.

## Accepted concepts

The project has accepted the following concepts at a high level, although their exact normative representation may remain open:

- support for raster representations;
- no hard dependency on a single raster codec;
- vector representations and/or overlays;
- text associated with image regions;
- the ability to record output from an external OCR system;
- OCR is not a built-in function of the format;
- password and secret fields must not be exposed through structured layers;
- structured regions;
- multiple annotation sets;
- relationships between entities;
- multiple representations;
- provenance;
- integrity and trust mechanisms;
- extensibility;
- safe skipping and, where possible, preservation of unknown extensions.

## Open architectural questions

The following questions are intentionally open:

- a custom container or an existing one;
- a profile built on an existing container;
- a hybrid approach;
- the final binary structure;
- object or chunk headers;
- endianness;
- magic bytes;
- MIME type;
- primary and backup indexes;
- CRCs and hashes;
- object identifiers;
- the exact logical object model;
- the text, font, and glyph fallback model;
- the exact provenance model;
- the integrity and trust model;
- conformance levels;
- the final SDK/API architecture.

These are open questions, not missing facts to be invented.

## Documentation model

Project documentation is maintained in English and Russian using mirrored structures, for example:

```text
docs/
├── en/
│   └── ...
└── ru/
    └── ...
```

At the next stage, new substantive research and design documents are prepared in Russian first. Their English versions are created after the structure has been discussed and the Russian text approved. Existing public English and Russian documents remain aligned with the factual project state.

For a future stable normative specification, the English version is expected to become normative and the Russian version to remain an official synchronized translation.

The project distinguishes these document classes:

- `PREP` — project preparation and baseline;
- `USE` — informative use-case description;
- `RSCH` — research;
- `REQ` — requirements;
- `DES` — design;
- `ADR` — architectural decisions;
- `SPEC` — normative specification;
- conformance material;
- glossary and terminology material;
- implementation material.

The base repository structure has been established. Additional directories are created as substantive material for the corresponding document classes appears.

## Licensing and brand context

The intended mixed licensing model is:

- Apache License 2.0 for source code, reference implementations, SDKs, tools, validation logic, and machine-readable implementation schemas unless stated otherwise;
- Creative Commons Attribution 4.0 International for specification text, research, requirements, design documents, ADR text, general documentation, and explanatory documentation graphics unless stated otherwise;
- a separate Brand Policy for the IMXO logo, Kumixo artwork, official brand illustrations, and other explicitly identified brand assets.

`LICENSES.md` records the scope. The license texts are present in `LICENSE` and `LICENSE-CC-BY-4.0.txt`. Brand assets are governed separately by `BRAND_POLICY.md`.

The project name is always written as **IMXO**. Its normative expansion is **Image Model eXchange Object**. Old or experimental expansions are not official.

Associations with IMHO or the Russian “ИМХО” are non-normative brand wordplay only.

Kumixo is the project's mascot and a brand concept. Kumixo images are not freely licensed documentation unless explicitly marked as such.

## Security and trust context

IMXO may contain structured data that does not fully match the visible pixels. Data contained in an IMXO object is not automatically trustworthy.

Relevant risks include discrepancies between visual and structured layers, malicious or misleading metadata, prompt-injection-like text, forged provenance, substituted annotations, leaked secrets, corrupted container data, parser weaknesses, and ambiguous verification state.

## OCR and text context

OCR is external to the format. An OCR system may write its output into IMXO structures, but IMXO itself is not an OCR engine and readers are not assumed to perform OCR.

The exact representation of fonts, glyph fallback, copyable text, text rendering fidelity, and complex writing systems remains open.

## Project state

`PREP-00` is complete. It records the initial baseline of accepted decisions and open questions.

The base `PREP-01` infrastructure is complete. The repository structure, licensing, Brand Policy, contribution and security infrastructure, and initial documentation structure are in place.

The next substantive steps are creation of the first real `USE` cards, preparation and approval of the initial systematic research plan, and only then the start of `RSCH` work. Technical research has not yet begun. Do not invent a research queue or reserve `RSCH` identifiers before the first use cases and an approved plan exist.

`PREP-05` is complete in synchronized Russian and English versions. The accepted Russian source in `docs/ru/project/PREP-05-decision-process.md`, as amended by PREP-08, uses the linked artifact classes `USE / Q / RSCH / REQ / DES / ADR / SPEC`. Each language tree contains a living `project/open-questions.md` index and mirrored question cards under `project/questions/`. GitHub Issues are the primary public entry point and coordination tool for external proposals and material public discussion, but an internal artifact may be created directly when an Issue adds no independent value. An Issue is not an accepted decision. Technical research under an approved program has not yet begun.

`PREP-06` is complete in synchronized Russian and English versions. It defines writing rules for the future specification without creating specification requirements or resolving open architecture. Normative language follows RFC 2119 and RFC 8174 (BCP 14) and is limited to `MUST`, `MUST NOT`, `SHOULD`, `SHOULD NOT`, and `MAY`. The supported table forms are Fixed Binary Layout, Logical / Variable Structure, and Bit / Flag Layout. Bidirectional traceability is maintained in a separate Informative Traceability Register, and Security Considerations and Privacy Considerations remain separate sections. PREP-06 does not decide byte order, text encoding, primitive types, or container layout.

`PREP-07` is complete in synchronized Russian and English versions, closing the initial `PREP-00` through `PREP-07` preparation baseline. The official project currently uses a Founder / Project Lead-led governance model; the Founder and Project Lead is Fyodor Malkov. Open participation does not create automatic decision authority, and maintainer status is granted by Project Lead invitation or delegation. The governance model should be reviewed when project scale or external adoption changes materially, but review triggers do not automatically transfer authority or create governance rights. `GOVERNANCE.md` is the official governance source and `IPR_POLICY.md` is the official IPR source. Ordinary contributions currently require no general CLA, DCO, or copyright assignment, and new governance or IPR obligations are not imposed retroactively on earlier contributors. `Q-0013` exists in synchronized Russian and English versions and remains `OPEN`; accessibility and regulatory adoption are research directions, not claims of legal compliance.

`PREP-08` is complete in synchronized Russian and English versions as a targeted process amendment made before systematic research began. `USE` is a separate Informative artifact class with identifiers `USE-0001...`, statuses `DRAFT / REVIEW / COMPLETE / WITHDRAWN / SUPERSEDED`, and dispositions `CANDIDATE / TARGET / NON-TARGET / DEFERRED`. `COMPLETE` is document maturity, not a support commitment or `ACCEPTED`; `TARGET` does not automatically create a requirement or v0.1 scope. Relationships among `USE`, `Q`, `RSCH`, and `REQ` are nonlinear and many-to-many. The future `docs/ru/project/research-plan.md` is a management document, not evidence or a technical decision source; there is no `PLAN-*` class, and research plans do not reserve `RSCH` identifiers. PREP-08 itself creates neither `USE-0001` nor a research plan and does not begin `RSCH` work.
