# PREP-00. IMXO Project Baseline

**Status:** DONE  
**Document type:** preparatory baseline  
**Purpose:** to capture the project state before systematic research, format architecture design, and specification development begin.

> This document is not the IMXO specification. It records decisions already accepted at the start of the project and separates them from questions that must be researched or designed in later stages.

---

## 1. Purpose of PREP-00

PREP-00 defines the initial project baseline before formal research and design begin.

The document is intended to:

- preserve already accepted decisions;
- avoid reopening basic questions without substantial new evidence;
- separate accepted decisions from open questions;
- define the boundary between preparation and later research;
- provide an initial reference point for requirements, design decisions, and the future specification.

All PREP-00 statements are divided into two categories:

- **ACCEPTED** — the decision has been accepted and is treated as a project baseline constraint;
- **OPEN** — the question remains unresolved and must be researched or designed later.

---

# 2. ACCEPTED — accepted decisions

## 2.1. Format name

Official format name:

**IMXO**

The name is always written using uppercase Latin letters.

Normative expansion:

**Image Model eXchange Object**

File extension:

`.imxo`

Informal associations with IMHO and the idea of open exchange of opinions may be used in communication and branding, but they are not a normative expansion of the name.

---

## 2.2. General goal

IMXO is intended to become an open international structured image format.

The format is not intended to be merely another way of storing pixels. Its purpose is to represent an image as an object that may contain multiple related representations and structured data layers.

The project is intended from the beginning for open development, a public specification, and independent implementations.

---

## 2.3. Static and passive model

The following principle is accepted for the first version of the standard:

**no executable or dynamic behavior inside the file.**

IMXO v0.1 must not contain:

- JavaScript;
- macros;
- executable scripts;
- event handlers;
- `onclick` or similar actions;
- automatic network requests;
- externally updated fields;
- embedded business logic;
- dynamically executed actions;
- animation or scripted behavior.

The file should remain static, passive, predictable, and suitable for safe parsing.

---

## 2.4. Raster representation

IMXO must support ordinary raster images.

The format must not be permanently tied to a single raster codec.

A specific image codec should be treated as a representation of content rather than as the identity of the IMXO format itself.

---

## 2.5. Vector data

IMXO must allow vector representations and/or vector overlays.

Raster and vector data must not be treated as mutually exclusive models.

---

## 2.6. Text layer

IMXO must allow text associated with an image and its regions to be stored.

At the conceptual level, this includes:

- text;
- coordinates or placement region;
- language;
- a relationship between the text and its visual representation;
- the ability to copy text without requiring OCR when reading the file.

The exact normative text model has not yet been defined.

---

## 2.7. OCR

OCR is not an embedded function of the format.

An external OCR system may analyze an image and write the result into the appropriate IMXO structures.

The format should define how the result is stored, but it is not required to implement recognition itself.

---

## 2.8. Secret and password fields

If the source system hides a password, secret, or other protected value, the mechanism producing an IMXO file must not reveal it through the text layer or another structured layer.

Structured representation must not become a side channel for obtaining data that was visually or systemically hidden from the user.

---

## 2.9. Regions

IMXO must support structured descriptions of image regions.

Regions may be used, for example, for:

- text;
- objects;
- user interface elements;
- annotations;
- semantic areas;
- user-created or machine-created selections.

The exact classification and normative region structure will be defined later.

---

## 2.10. Annotations

The format must allow multiple annotation sets.

Annotations may originate from different sources, including:

- a user;
- an application;
- a server;
- a camera or device;
- a computer vision system;
- an AI system;
- an imported external format.

IMXO must not be restricted to a single annotation system.

---

## 2.11. Relationships between entities

The format must allow relationships between objects, regions, representations, text, annotations, and other structured entities.

The exact reference and relationship model has not yet been fixed.

---

## 2.12. Multiple representations

A single IMXO object may contain multiple representations of the same image or associated data.

This may be used for different:

- raster representations;
- vector representations;
- quality levels;
- auxiliary layers;
- derived data;
- specialized representations for different systems.

---

## 2.13. Provenance

IMXO must allow the origin of data to be described.

It should be possible to determine who or what produced a particular piece of structured data.

The exact provenance model will be designed separately.

---

## 2.14. Integrity and trust

The IMXO architecture must provide mechanisms for integrity and trust verification.

In particular, it should be possible to detect inconsistency between visible image content and associated structured layers.

The exact cryptographic and object model has not yet been defined.

---

## 2.15. Extensibility

The format must be designed for future evolution.

Unknown extensions should, where possible:

- be recognized as unknown;
- be skipped safely by implementations;
- be preserved across read/write operations when the implementation does not modify them.

Extensibility should not require a complete redesign of the format when new data types are introduced.

---

## 2.16. Research of existing containers

Existing container architectures and formats must be researched before the physical and detailed logical models of IMXO are finalized.

The research must include at least:

- JUMBF / JLINK;
- ISO BMFF / HEIF;
- RIFF;
- PNG chunks;
- TIFF / BigTIFF;
- ZIP-like container models;
- other relevant container solutions identified during the research.

This research must precede the final decision to use a custom container or build on an existing one.

---

## 2.17. Design sequence

The following overall direction is accepted at this stage:

1. project preparation;
2. research of existing standards and containers;
3. refinement of requirements;
4. selection or design of the physical model;
5. design of the logical model;
6. recording of architectural decisions;
7. development of the normative specification;
8. preparation of a reference implementation, test data, and conformance validation.

The detailed stage structure will be defined separately.

---

# 3. OPEN — unresolved questions

## 3.1. Container architecture

No final decision has yet been made between:

- a fully custom IMXO container;
- a profile or layer built on an existing container;
- a hybrid approach.

The decision must be made only after alternatives have been researched.

---

## 3.2. Physical file structure

The following are not yet finalized:

- file signature;
- endian;
- global header;
- header size;
- block/chunk header structure;
- `type`;
- size rules;
- use of `uint64`;
- `object_id`;
- flags;
- header CRC;
- content CRC;
- cryptographic hashes;
- nesting;
- footer;
- primary index;
- backup index;
- recovery sync marker;
- padding;
- alignment;
- rules for bypassing damaged data;
- preservation rules for unknown blocks.

---

## 3.3. Logical object model

The exact logical structure of IMXO has not yet been fixed.

The following must be defined:

- base object types;
- mandatory and optional entities;
- relationships between entities;
- identifiers;
- references;
- data ownership;
- nesting;
- extension lifecycle;
- rules for serializing the logical model into the container.

---

## 3.4. MIME type, magic, and brand

The following are not yet defined:

- MIME type;
- magic bytes;
- possible container brand;
- rules for identifying version and profile.

---

## 3.5. Versioning

The normative versioning model has not yet been defined for:

- the format;
- the container;
- the logical model;
- extensions;
- profiles;
- compatibility between versions.

---

## 3.6. Text, fonts, and glyph fallback

The following must be determined:

- whether fonts should be embedded;
- when embedding is allowed;
- licensing constraints;
- whether glyph raster fallback is required;
- fallback rules;
- the relationship between displayed text and copyable text;
- behavior when the original font is unavailable;
- rules for complex writing systems.

---

## 3.7. Provenance model

The following must be defined:

- provenance structure;
- required granularity;
- source identification;
- transformation chains;
- trusted and untrusted sources;
- provenance inheritance rules;
- interaction between provenance, hashes, and signatures.

---

## 3.8. Integrity / Trust model

The project must define:

- hashing model;
- hash scope;
- relationship between visual and structured representations;
- indicators of modified or unverified data;
- a user-facing trust indicator;
- partial verification rules;
- possible support for digital signatures.

---

## 3.9. Computer Vision annotations

Compatibility with existing systems and schemas must be researched, including:

- YOLO;
- COCO;
- bounding boxes;
- polygons;
- masks;
- points;
- labels;
- confidence values;
- additional object properties.

It must be determined which structures are normative IMXO concepts and which are mappings from external schemas.

---

## 3.10. Accessibility

A normative accessibility model must be defined, including:

- alt-like description;
- image-level description;
- descriptions of individual regions;
- language attributes;
- relationships with text and semantic layers.

---

## 3.11. SDK and integrations

PREP-00 does not define final decisions for:

- SDKs;
- APIs;
- Windows;
- Linux;
- macOS;
- Android;
- browsers;
- Photoshop;
- GIMP;
- Krita;
- system image viewers;
- screenshot tools.

These questions will be addressed later after the core models are sufficiently stable.

---

## 3.12. Conformance

The following have not yet been defined:

- conformance levels;
- mandatory decoder capabilities;
- mandatory encoder capabilities;
- behavior for unknown extensions;
- test suites;
- reference files;
- validation rules.

---

# 4. What PREP-00 intentionally does not decide

PREP-00 must not:

- choose the container;
- design the binary structure;
- define the final logical model;
- fix specific hashing algorithms;
- define the final API;
- design the SDK;
- describe the final specification;
- choose specific implementation libraries.

All such decisions must be based on later research.

---

# 5. Completion criterion

PREP-00 is considered complete when:

- accepted baseline decisions have been collected;
- open questions have been explicitly listed;
- the boundary between preparation and research has been defined;
- no new architectural decisions are introduced inside PREP-00 unless the baseline itself needs revision.

**State at the time of capture: PREP-00 DONE.**

Next stage:

**PREP-01 — project and repository structure.**
