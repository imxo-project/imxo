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

Russian may be the working language during the early stages. English is maintained as the international project language.

For a future stable normative specification, the English version is expected to become normative and the Russian version to remain an official synchronized translation.

The project distinguishes these document classes:

- `PREP` — project preparation and baseline;
- `RSCH` — research;
- `REQ` — requirements;
- `DES` — design;
- `ADR` — architectural decisions;
- `SPEC` — normative specification;
- conformance material;
- glossary and terminology material;
- implementation material.

The final repository tree remains open.

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

The current focus is:

- finalizing the repository structure;
- documenting the licensing model;
- preparing the README and contribution infrastructure;
- adding the initial brand assets;
- organizing PREP documents;
- preparing the research plan;
- then beginning systematic container research.
