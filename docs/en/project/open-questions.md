# IMXO Open Questions

This document is a living registry of material project questions that have not yet received a final resolution.

The initial questions were transferred from `PREP-00`.

PREP-00 remains an immutable historical checkpoint. The current state of these questions is tracked here.

## Rules

Allowed statuses:

- `OPEN`;
- `RESOLVED`;
- `SUPERSEDED`.

`Q-xxxx` identifiers are never reused.

A question is not removed after it is closed.

## Q-0001 — IMXO container architecture

**Status:** OPEN  
**Area:** Container  
**Source:** PREP-00

Determine whether IMXO should use a fully custom container, a profile or layer built on an existing container, or a hybrid approach.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0002 — Physical file structure

**Status:** OPEN  
**Area:** Container  
**Source:** PREP-00

Define the signature, endianness, headers, type, size, object identifiers, flags, CRCs/hashes, nesting, footer, indexes, recovery markers, padding/alignment, damage handling, and preservation of unknown blocks.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0003 — Logical object model

**Status:** OPEN  
**Area:** Logical model  
**Source:** PREP-00

Define the base object types, mandatory and optional entities, relationships, identifiers, references, nesting, data ownership, extensions, and mapping of the logical model into the container.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0004 — MIME type, magic, and brand

**Status:** OPEN  
**Area:** Identification  
**Source:** PREP-00

Define the MIME type, magic bytes, possible container brand, and version/profile identification rules.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0005 — IMXO versioning

**Status:** OPEN  
**Area:** Versioning  
**Source:** PREP-00

Define the versioning model for the format, container, logical model, extensions, profiles, and compatibility between versions.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0006 — Text, fonts, and glyph fallback

**Status:** OPEN  
**Area:** Text  
**Source:** PREP-00

Define font embedding, licensing constraints, glyph raster fallback, the relationship between displayed and copyable text, behavior when the original font is unavailable, and support for complex writing systems.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0007 — Provenance model

**Status:** OPEN  
**Area:** Provenance  
**Source:** PREP-00

Define the provenance structure, granularity, source identification, transformation chains, trusted and untrusted sources, inheritance, and interaction with hashes and signatures.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0008 — Integrity / Trust model

**Status:** OPEN  
**Area:** Security / Trust  
**Source:** PREP-00

Define the hashing model, hash scope, relationship between visual and structured representations, indicators of modified or unverified data, trust indicators, partial verification, and possible digital signatures.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0009 — Computer Vision annotations

**Status:** OPEN  
**Area:** Annotations / CV  
**Source:** PREP-00

Research compatibility with YOLO, COCO, bounding boxes, polygons, masks, points, labels, and confidence values, and determine the boundary between normative IMXO concepts and mappings from external schemas.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0010 — Accessibility model

**Status:** OPEN  
**Area:** Accessibility  
**Source:** PREP-00

Define a normative model for alt-like descriptions, image and region descriptions, language attributes, and relationships with text and semantic layers.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0011 — SDKs and integrations

**Status:** OPEN  
**Area:** Implementation  
**Source:** PREP-00

Define the future model for SDKs, APIs, platform integrations, viewer/editor integration, browsers, and capture tools after the core architecture stabilizes.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0012 — Conformance model

**Status:** OPEN  
**Area:** Conformance  
**Source:** PREP-00

Define conformance levels, mandatory decoder and encoder capabilities, behavior for unknown extensions, test suites, reference files, and validation rules.

**Research:** not assigned  
**Resolution:** not resolved

## Adding new questions

New material questions receive the next permanent identifier: `Q-0013`, `Q-0014`, and so on.
